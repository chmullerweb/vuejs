<template>
  <div class="exercise-4">
  <Bouton msgAlert="Waza!">Text 1</Bouton>
  <Bouton>Text 2</Bouton>
  <Bouton></Bouton>
  <hr>
  <Book>
  <template v-slot:titleBook>
    <h1>Here might be a title Book</h1>
  </template>
  </Book>
  </div>
</template>

<script>
import Bouton from "./Bouton.vue";
import Book from "./Book.vue";

export default {
  name: "Exercise4",
  components: {Bouton, Book}
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-4 {
  color: $grey;
}


</style>
