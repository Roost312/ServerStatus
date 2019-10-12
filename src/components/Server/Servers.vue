<template>
  <div class="col-xs-12 col-sm-6">
    <!--printing the list created in the the servers.vue file-->
     <!--  :server = "s" is updating the server variable in the server.vue file-->
    <ul class="list-group">
      <app-server 
      v-for="s in servers"
      :server="s">
      </app-server>
    </ul>
  </div>
</template>

<script>
import Server from './Server.vue';

export default {
  data () {
    return {
      servers: [
        { id: 1, status: 'Normal' },
        { id: 2, status: 'Critical' },
        { id: 3, status: 'Unkown' },
        { id: 4, status: 'Normal' }
      ]
    }
  },
  components: {
    appServer: Server
  }
}
</script>

<style>

</style>
