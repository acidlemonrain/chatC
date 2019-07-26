<template>
  <div>
    <v-container v-if="username ===' '">
      <v-text-field v-model="tname" label="your name?"></v-text-field>
      <v-btn outline @click="sure">confirm</v-btn>
    </v-container>
    <v-container v-if="username !== ' '">
      <v-layout justify-center>
        <v-flex md12>
          <v-card width="100%" style="position:relative;border:1px solid #ccc" flat>
            <v-layout>
              <v-flex md8>
                <v-container>
                  <v-layout column>
                    <p>msgs</p>
                    <v-list subheader two-line style="height:50vh" class="msgs" column id="msg">
                      <v-list-tile v-for="(msg,index) in msgs" :key="index">
                        <v-list-tile-content>
                          <v-list-tile-title>{{msg.user}}</v-list-tile-title>
                          <v-list-tile-sub-title>{{msg.data}}</v-list-tile-sub-title>
                        </v-list-tile-content>
                      </v-list-tile>
                    </v-list>

                    <v-textarea
                      class="ma-0"
                      label="One row"
                      auto-grow
                      outline
                      rows="1"
                      row-height="15"
                      v-model="msg"
                    ></v-textarea>

                    <v-layout class="ma-0">
                      <v-spacer></v-spacer>
                      <v-btn @click="chat" outline>send</v-btn>
                    </v-layout>
                  </v-layout>
                </v-container>
              </v-flex>

              <v-flex md4 class="hidden-sm-and-down">
                <v-container>
                  <v-layout>
                    <v-card flat width="100%">
                      <p small>online</p>
                      <v-list column one-line style="height:65vh" class="msgs">
                        <v-list-tile v-for="(user,index) in userlist" :key="index">
                          <div>{{user.name}}</div>
                        </v-list-tile>
                      </v-list>
                    </v-card>
                  </v-layout>
                </v-container>
              </v-flex>
            </v-layout>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";
import io from "socket.io-client";
export default {
  data: () => {
    return {
      username: " ",
      userlist: [],
      tname: "",
      msg: "",
      socket: {},
      msgs: [],
      sum: 0,
      isconnect: "waiting for server"
    };
  },
  created() {
    this.socket = io("http://106.15.183.147:8001");
  },
  mounted() {},
  destroyed() {
    this.socket.disconnect();
  },
  methods: {
    chat() {
      this.socket.emit("chatting", this.username, this.msg);
      this.msg = "";
    },
    sure() {
      this.username = this.tname;
      this.socket.emit("username", this.username);
      // listen on shake init
      this.socket.on("shake", res => {
        this.isconnect = "connet to serve";
        this.sum = res.sum;
        this.msgs = res.msgs;
        this.userlist = res.userlist;
      });
      //on msg
      this.socket.on("msg", msg => {
        this.msgs.push(msg);
        var element = document.getElementById("msg");
        setTimeout(() => {
          element.scrollTop = element.scrollHeight;
        }, 20);
        console.log(msg);
      });
    }
  }
};
</script>
<style scoped>
.msgs {
  overflow-y: scroll;
  margin-bottom: 1rem;
}
.bottom {
}
</style>
