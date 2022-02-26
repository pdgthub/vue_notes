<template>

  <div>
  <h3 style="margin-bottom:0px;">
    New Note
  </h3>
      <form @submit.prevent="addNote">
          <div>
          <input type="text" v-model="title" name="title" placeholder="Title">
          </div>
          <div>
          <textarea rows = "10" cols = "15" v-model="text" name = "text" placeholder="Note"></textarea>
          <input type="submit" value="Add" class="btn">
          </div>          
      </form>
  </div>
</template>

<script>
import * as uuid from 'uuid';
export default {
    name: "AddNote",
    data() {
        return {
            title: '',
            text: '',
        }
    },
    methods: {
        addNote(e) {
            e.preventDefault();
            const newNote = {
                id: uuid.v4(),
                title: this.title,
                text: this.text,
                completed: false,
            }
            this.$emit('add-note', newNote);
        }
    }

}
</script>

<style>

</style>