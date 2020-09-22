<template>
  <div class="btn">
    <button type="submit" @click="bidule()">
        <slot>Default Text</slot>
    </button>
  </div>
</template>

<script>
export default {
  name: "Bouton",
  methods: {
      bidule() {
          alert(this.msgAlert);
      }
  },
  props: {
      msgAlert: {
          type: String,
          default: "Coucou!",
      } 
  }
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

button{
  margin: 2rem 0;
}

button:first-child{
  color : blue
}

</style>