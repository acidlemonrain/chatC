<template>
  <div>
    <atom-spinner :animation-duration="4500" :size="600" :color="'#ccc'" />
  </div>
</template>

<script>
import Vuetable from "~/plugins/table.js";
import axios from "axios";
import { AtomSpinner } from "epic-spinners";
export default {
  components: {
    Vuetable,
    AtomSpinner
  },
  data: () => {
    return {
      fields: [
        {
          name: "__handle",
          titleClass: "center aligned",
          dataClass: "center aligned"
        },
        {
          name: "__sequence",
          title: "#",
          titleClass: "center aligned",
          dataClass: "right aligned"
        },
        {
          name: "__checkbox",
          titleClass: "center aligned",
          dataClass: "center aligned"
        },
        {
          name: "name",
          sortField: "name"
        },
        {
          name: "email",
          sortField: "email"
        },
        {
          name: "birthdate",
          sortField: "birthdate",
          titleClass: "center aligned",
          dataClass: "center aligned",
          callback: "formatDate|DD-MM-YYYY"
        },
        {
          name: "nickname",
          sortField: "nickname",
          callback: "allcap"
        },
        {
          name: "gender-slot",
          title: '<i class="grey heterosexual icon"></i>Gender',
          titleClass: "center aligned",
          dataClass: "center aligned",
          width: "15%"
        },
        {
          name: "salary",
          sortField: "salary",
          titleClass: "center aligned",
          dataClass: "right aligned",
          callback: "formatNumber"
        },

        {
          name: "__slot:actions",
          title: "Slot Actions",
          titleClass: "center aligned",
          dataClass: "center aligned"
        }
      ],
      localData: ""
    };
  },
  created() {
    axios.get("https://vuetable.ratiw.net/api/users").then(res => {
      this.localData = res.data;
    });
  }
};
</script>
