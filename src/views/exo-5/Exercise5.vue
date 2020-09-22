<template>
  <div class="exercise-5">
    <h1>Les restos de Toulouse</h1>
    <h2>Liste des restos de Toulouse</h2>
    <button @click="showResto">Voir la liste des restaurants</button>
    <ul v-for="resto in restos" :key="resto.id">
        <li>{{resto.nom}}</li>
        <li>{{resto.type}}</li>
        <li v-if="resto.adresse !== '?'">{{resto.adresse}}</li>
        <li v-if="resto.telephone !== '?'">{{resto.telephone}}</li>
   </ul>
   <hr>
   <h2>Ajouter un restaurant à la liste</h2>
   <form method="post">
   <label for="nom">Nom du restaurant</label>
   <input name="nom"><br><br>
   <label for="type">Type de cuisine</label>
   <input name="type"><br><br>
   <label for="adresse">Adresse du restaurant</label>
   <input name="adresse"><br><br>
   <label for="telephone">Numéro de téléphone</label>
   <input name="telephone"><br><br>
   <label for="plats">Plats du chef</label>
   <input name="plats"><br><br>
   <button type="submit" @click="addResto">Ajouter un restaurant à la liste</button>
   </form>
  </div>
</template>

<script>
      const axios = require('axios');


export default {
  name: "Exercise5",
  data() {
    return {
      restos: [],
    }
  },
  methods: {
    showResto() {
      axios.get('https://restop-toulouse.herokuapp.com/restos').then((resp) => {
        this.restos = resp.data
      }).catch((err) => {
        console.log(err);
      })
    },
    async showResto() {
      try {
      const listeResto = await axios.get('https://restop-toulouse.herokuapp.com/restos');
      this.restos = listeResto.data;
      ou
      this.restos = (await axios.get('https://restop-toulouse.herokuapp.com/restos')).data;
    } catch(err) {
      console.log(err);
    }
    }
    addResto(){
      axios.post('https://restop-toulouse.herokuapp.com/restos').then((resp) => {
        console.log(resp);
      }).catch((err) => {
        console.log(err);
      })
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '../../theme.styl';

.exercise-5 {
  color: $grey;
}
</style>
