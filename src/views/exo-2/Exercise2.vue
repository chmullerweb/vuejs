<template>
  <div class="exercise-2">
    <div class="card" v-for="user in users" :key="user.id">   
        <div class="flex">
            <h2>{{ user.firstname + " " + user.lastname }}</h2>
            <img v-bind:src="img + user.id"/>
        </div>
        <h6> {{ fullName(user.firstname, user.lastname) }}</h6>
        <p> {{ user.email }}</p>
        <p> {{ user.password }}</p>
        <div v-bind:class="{premium: user.premium}" v-if="user.premium === true">
          <p>Vous êtes un membre premium</p>
        </div>
        <div>
          <button type="button" @click="user.premium = !user.premium" v-if="user.premium == false">Devenir Premium</button>
          <button type="button" @click="user.premium = !user.premium" v-if="user.premium == true">Ne plus être Premium</button>
        </div>
        <button type="button" class="deleteBtn" @click="deleteCard(user)">Supprimer</button>
    </div>
  </div>
</template>



<script>
import { users } from "./data";

export default {
  name: "Exercise2",

  data() {
    return {
      users: users,
      lastname: users[0].lastname,
      firstname: users[0].firstname,
      img: 'http://lorempixel.com/400/200/people/',
      delete: false
    };
  },
  computed: {
    //on utilise this quand on fait référence au data du composant
    fullNamebis() { return this.lastname + " " + this.firstname},
  },
  methods: {
    fullName(firstname, lastname) {
      return `${firstname} ${lastname}`;
  },
    deleteCard(user) {
      //on nomme l'évènement, la value qui attribuée lors de l'évent
      this.$emit("deleteUser", user);
      console.log(` ${user.lastname} a été supprimé(e)`)
    },
    bePremium(userPremiumness){
       return userPremiumness = !userPremiumness;
   }
  }
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.flex{
  display: flex;
}

img{
  width: auto;
    height: 5rem;
    padding: 0.3rem;
}

.exercise-2 {
  color: $grey;
}

.card{
  width: 30rem;
  height: auto;
  margin-bottom: 3rem;
  padding-bottom: 1rem;
  background-color: grey;
}

.premium{
  color: yellow;
}

button.deleteBtn{
  color : red
  margin-top: 0.6rem;
  font-weight : bold;
}


h2{
  padding: 1.5rem 0 1rem 0;
  border-bottom: 1px solid aqua;
  width: 30rem;
}
</style>
