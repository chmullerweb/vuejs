<template>
  <div class="claim">
  <h1><slot name="titleBook">Titre du livre</slot></h1>
  <button><slot name="moreBtn">En savoir plus</slot></button>
  <p><slot name="extractBook">Marzipan marzipan chocolate cake croissant carrot cake jelly-o caramels. Soufflé halvah bonbon gummi bears jelly beans wafer candy canes. Chupa chups liquorice wafer pastry. Jelly-o cheesecake bear claw chocolate cheesecake apple pie muffin chocolate.</slot></p>
  </div>
</template>


<script>
export default {
  name: "Book",
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';



</style>