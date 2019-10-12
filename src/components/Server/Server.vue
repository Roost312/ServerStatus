<template>
    <li @click="passStatus"
        style="cursor: pointer"
        class="list-group-item">
        Server #{{ server.id }}
    </li>
</template>

<script>
/*bring in serverBus to update variable between server and serverDetails*/
import { serverBus } from '../../main.js';

export default {
    //changes server between parent and child....Servers.vue is parent
    props: ['server'],
    methods: {
        passStatus() {
            console.log("server.vue passStatus() function ran");
            /*updating the event bus*/
            console.log(this.server,"server from server.vue");
            serverBus.$emit('serverSelected', this.server);
            console.log("emited bus");
        }
    }
}
</script>
<style>
   
</style>

