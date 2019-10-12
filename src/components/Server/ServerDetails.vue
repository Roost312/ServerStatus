<template>
  <div class="col-xs-12 col-sm-6">
    <p v-if="!server">Please select a server</p>
    <p v-else>Server # {{ server.id }} selected, Status: {{ server.status }}</p>
    <hr>
    <button @click="resetStatus">Change to Normal</button>
  </div>

</template>

<script>
import { serverBus } from '../../main.js';

export default {
  data () {
    return {
      server: null
    }
  },
  methods: {
    resetStatus () {
      console.log("reset server status to normal");
      this.server.status = 'Normal';
    }
  },
  //created is called each time event bus is updated
  created() {
    serverBus.$on('serverSelected', (server) => {
      console.log("created() server.$on in ServerDetails");
      this.server = server;
      console.log(this.server,"current this.server from serverdetails");
    })
  }
}
</script>

<style>

</style>
