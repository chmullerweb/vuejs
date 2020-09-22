<template>
    <div>
        <button :class="{'redError': hasError, 'green': green, 'btnColor': !green}">{{title}}</button>  <!--mettre !hasError si on veut que ce soit false -->
        <p v-if="hasError">{{error}}</p>
    </div>
</template>

<script>
export default {
  name: "Bouton",
  props: {
     hasError:{
         type:Boolean,
         default: false
     },
     error:{
         type:String,
         default: ""
     },
     green: {
         type: Boolean,
         default: false
     },
     title: {
         type: String,
         required: true
    },
  }
};
</script>

<style>
.redError{
    border: 2px solid red;
}

.green{
    background-color: green;
    color: white;
}

.btnColor{
    background-color: white;
    color: grey;
}

</style>

