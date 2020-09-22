<template>
    <div class="client">
        <div v-for="user in users" :key="user.id">
        <router-link  :to="`/users/${user.id}`">
        <h1>{{user.firstname}} {{user.lastname}} - {{user.id}}</h1>
        </router-link>
        <p>Informations générales :</p>
            <ul>
                <li>Nom : {{user.lastname}}</li>
                <li>Prénom : {{user.firstname}}</li>
                <li>Email : {{user.email}}</li>
                <li>Password : {{user.password}}</li>
            </ul>
        </div>
        
        <button @click="showExo1">Aller à l'exercice 1</button>
        <br><br>
        <router-link to="/exo-2"><button>Aller à l'exo 2 via router-link</button></router-link>
        <br><br>
        <button @click="showAnne">Salut Anne !</button>

    </div>
</template>



<script>
//J'importe mon fichier data.js et le renseigne dans la data() du composant
import { membres } from "../data";


export default {
  name: 'Users',
  data() {
    return {
      users: membres,
    }
  },
  props: {
        identifiantClient: Number,
        nom: {
            type: String,
            default: ""
        },
        prenom: {
            type: String,
            default: ""
        },
        adresse: String,
        email: {
            type: String,
            default: ""
        } 
  },
  computed: {
      fullName() { return this.firstname + this.lastname }
  },
  methods: {
      showExo1() {
          this.$router.push({path: `/exo-1`})
      },
      showAnne() {
          this.$router.push({path: `/users/3`})
      },
  },
};
</script>