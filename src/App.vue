<template>
  <div id="app">
  <Header />
  <List v-bind:notes="notes" v-on:del-note="deleteNote"/>
  <AddNote v-on:add-note="addNote"/>

    
  </div>
</template>

<script>
import Header from './components/Header';
import List from './components/List';
import AddNote from './components/AddNote';


export default {
  name: 'App',
  components: {
    List,
    Header,
    AddNote,

  },
  data() {
    return {
      notes: [
        {
          id: 1,
          title: 'laundry reminder',
          text: 'remember to do the laundry this weekend'
        },
        {
          id: 2,
          title: 'gym notes',
          text: 'bench: 75; squat: 95; ohp: 60; go up on ohp',
        },
        {
          id: 3,
          title: 'goal for this month',
          text: 'read one book a week',
        }

      ]
    }
  },
  created: function () {
    // `this` points to the vm instance
    this.notes = JSON.parse(localStorage.getItem("notes"));
  },
  methods: {
    deleteNote(id) {
      this.notes = this.notes.filter(note => note.id !== id);
    },
    addNote(newNote) {
      this.notes = [...this.notes, newNote];
      localStorage.setItem("notes", JSON.stringify(this.notes));
    }
  }
}
</script>

<style>

</style>
