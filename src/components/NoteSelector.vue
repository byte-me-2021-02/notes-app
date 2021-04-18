<template>
  <div 
    class="note-selector" 
    v-bind:class="{active: note.id === selectedNoteId}"
    v-on:click="selectNote(note)"
  >
    <p class="note-selector-title">{{note.body}}</p>
    <p class="note-selector-timestamp">{{note.timestamp}}</p>
  </div>
</template>

<script> 
export default {
  props: ["note", "selectedNoteId"],
  methods: {
    selectNote: function(note) {
      // this.selectedNoteId = note.id;
      this.$emit("selectNote", note);
    }
  }
}
</script>