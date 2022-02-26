<template>
<div>
  <div v-bind:key="note.id" v-for="note in notes">
      <ListItem v-bind:note="note" />
      <Delete v-bind:note="note" v-on:del-note="$emit('del-note', note.id)"/>
      </div>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';
import Delete from './Delete.vue';
export default {
    name: "List",
    components: {
        ListItem,
        Delete,
        
    },
    props: ["notes"] /* type, required */

}
</script>

<style scoped>
.list-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
    width: 40%;
    text-align: left;
  }
</style>