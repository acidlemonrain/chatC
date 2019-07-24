<template>
  <v-container>
    <v-layout justify-center align-center>
      <v-flex xs12 sm8 md6 v-if="username == ''">
        <div class="loginmodule">
          <v-text-field v-model="tname" label="your name"></v-text-field>
          <v-btn @click="sure">sure</v-btn>
        </div>
      </v-flex>

      <v-flex xs12 md11 class="chatmodule" v-if="username!=''">
        <div class="text-xs-center">{{isconnect}}</div>
        <v-layout justify-space-between wrap>
          <v-flex xs10 md5>
            <div class="msg" id="msg">
              <div v-for="(msg,index) in msgs" :key="index">
                <div v-if="msg.user ==  username" style="color:red">{{msg.user}}:</div>
                <div v-if="msg.user != username" style="color:blue">{{msg.user}}:</div>
                <v-card class="pa-2">{{msg.data}}</v-card>
              </div>
            </div>
            <v-text-field v-model="msg" label="msg" required></v-text-field>
            <v-btn flat @click="chat">send</v-btn>
          </v-flex>
          <v-flex xs12 md5>
            <h4>total man : {{sum}}</h4>
            <h4 v-for="user in userlist" :key="user" style="color:purple">{{user.name}}</h4>
          </v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";
import socket from "~/plugins/socket.io.js";
export default {
  data: () => {
    return {
      username: "",
      userlist: [],
      tname: "",
      msg: "",
      msgs: [],
      sum: 0,
      isconnect: "waiting for server"
    };
  },
  mounted() {},
  methods: {
    chat() {
      socket.emit("chatting", this.username, this.msg);
      this.msg = "";
    },
    sure() {
      this.username = this.tname;
      socket.emit("username", this.username);
      // listen on shake init
      socket.on("shake", res => {
        this.isconnect = "connet to serve";
        this.sum = res.sum;
        this.msgs = res.msgs;
        this.userlist = res.userlist;
        console.log(this.userlist);
      });
      //on msg
      socket.on("msg", msg => {
        this.msgs.push(msg);
        var element = document.getElementById("msg");
        setTimeout(() => {
          element.scrollTop = element.scrollHeight;
        }, 20);
      });
    }
  }
};
</script>
<style scoped>
.msg {
  height: 200px;
  overflow-y: scroll;
}
</style>
