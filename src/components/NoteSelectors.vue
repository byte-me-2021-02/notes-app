<template>
  <div class="note-selectors">
    <NoteSelector 
      v-for="note in notes" 
      v-bind:note="note" 
      v-bind:key="note.id" 
      v-bind:selectedNoteId="selectedNoteId" 
      v-on:selectNote="selectNote"
    />
  </div>
</template>

<script>
import NoteSelector from "./NoteSelector.vue"
export default {
  props: ["notes", "selectedNoteId"],
  data: function() {
    return {
      
    }
  },
  methods: {
    selectNote: function(note) {
      this.$emit("selectNote", note)
    }
  },
  components: {
    NoteSelector
  }
}
</script>