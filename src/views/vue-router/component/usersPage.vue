<template>
    <div class="client">
        <h1>{{userSelected.firstname}} {{userSelected.lastname}} - {{users.id}}</h1>
        <p>Informations générales :</p>
            <ul>
                <li>Nom : {{userSelected.lastname}}</li>
                <li>Prénom : {{userSelected.firstname}}</li>
                <li>Email : {{userSelected.email}}</li>
                <li>Password : {{userSelected.password}}</li>
            </ul>
    </div>
</template>



<script>
//J'importe mon fichier data.js
import { membres } from "../data";


export default {
  name: 'Users',
  data() {
    return {
      users: membres,
      idUserSelected: 0,
      userSelected: {}
    }
  },
  computed: {
      fullName() { return this.firstname + this.lastname }
  },
  mounted() {
      //on récupère le params.id qui est dans l'url grâce à l'objet $route
      this.idUserSelected = this.$route.params.id,
      //on sélectionne l'user à afficher selon son id grâce à la fonction find
      this.userSelected = this.users.find((user) => user.id == this.idUserSelected);
  },
};
</script>