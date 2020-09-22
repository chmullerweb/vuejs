<template>
  <div class="exercise-3">
  <Bouton :hasError="true" error="Il y a une erreur" title="Bouton blanc et gris"></Bouton>
  <Bouton :hasError="false" title="Ceci un autre bouton" green></Bouton>
  </div>
</template>

<script>
import Bouton from "./Bouton.vue";

export default {
  name: "Exercise3",
  components: {Bouton},
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-3 {
  color: $grey;
}
</style>
