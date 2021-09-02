<template>
  <div class="formulaire">
    <h2>Compteur de mot</h2>
    <form>
      <div class="item">
        <label for="msg"> Entrez vos mots :</label>
      </div>
      <div class="item">
        <textarea v-model="texte" name=""></textarea>
      </div>
      <div class="item">
        <a v-on:click="calculMot()"> Valider</a>
      </div>
    </form>

    <p v-if="resultatBool == true">
      Résultat du nombre de mot : {{ listeMots.length }}
      <br />
      Avec comme séparateur l'espace
    </p>

    <div v-for="item, id in listeMots" :key="id" class="listeMot">
      <p>{{ item }}</p>
      <a v-on:click="supprimerMot(id)" class="delete"> Supprimer le mot </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Compteur",
  data: function () {
    return {
      texte: "",
      resultatBool: false,
      listeMots: [],
      tableauValMax: [],
      compteur: 0,
    };
  },
  methods: {
    calculMot() {
      this.listeMots = this.texte.split(" ");
      this.resultatBool = true;
      console.log("fonction calculerMot()",this.listeMots);
      console.log("fonction calculerMot()", this.listeMots.length)


      // for(var i=0; i<this.listeMots.length; i++){
      //   console.log(this.listeMots[i])

      //   // for(var i=0;)
      //   if(this.listeMots[i] == this.listeMots[i+1]){
      //     this.compteur++
      //     this.tableauValMax.push(this.listeMots[i])
      //   }

      // console.log(this.compteur, this.tableauValMax)
      // }
    },
    supprimerMot(id) {
        console.log("fonction supprimermot", id)
        this.listeMots.splice(id, 1)      
      }
    }
};
</script>

<style scoped>
.formulaire {
  text-align: center;
}
.formulaire form {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}
.formulaire form .item {
  margin: 10px 0;
}
.formulaire .item textarea {
  width: 300px;
  height: 200px;
  resize: none;
}
.formulaire .item a {
  width: 30px;
  height: 20px;
  cursor: pointer;
  padding: 5px;
  border: 1px solid #000;
}
.listeMot{
  display: flex;
  justify-content: center;
}
.listeMot p {
  font-size: 16px;
  margin: 0 5px;
  color: green;
}
.listeMot .delete {
  font-size: 14px;
  margin: 2px 0;
  color: red;
  cursor: pointer;
}
</style>
