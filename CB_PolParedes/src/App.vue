<script setup>
import {ref, reactive} from 'vue'
//Ref exemple (Valid per tipus simples de variables)
const num= ref(0)
const incrementar = () =>{
  num.value++
}
//Reactive exemple (Valid per tipus no simples de variables)
const usuari=reactive({
  nom:'pol',
  edat: 19
})

const augmentarEdat=()=>{
  usuari.edat++
}

//Exemple directiva v-bind
const titol="hola"
const imatgeUrl= ref("https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/653.png")
const canviar = ()=>{
  imatgeUrl.value= "https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/700.png"
}

//Exemple directiva v-mode
const nomUsuari=ref('')

//Exemple directiva v-for
const productes=[
  {
    id:1,
    nom:"Pila",
    preu:6
  },
  {
    id:2,
    nom:"Poma",
    preu:8
  },
  {
    id:3,
    nom:"Aigua",
    preu:31
  }
]

// Exemple directiva v-if v-else
const logat=ref(false)

//Exemple directiva v-show
const mostrar=ref(false)

//Directiva v-on = @
</script>

<template>
  <div>
    <h1>Exemple ref</h1>
    <h3>{{ num }}</h3>
    <button @click="incrementar">Incrementar</button>
  </div>
  
  <div>
    <h1>Exemple reactive</h1>
    <p>{{ usuari.nom }}</p>
    <p>{{ usuari.edat }}</p>
    <button @click="augmentarEdat">Augmentar edat</button>
  </div>
  
  <div>
    <h1>Exemple V-bind</h1>
    <h2 v-bind:title="titol">Possa el ratoli per sobre</h2>
    <img  :src="imatgeUrl"  alt="imagen" @click="canviar">
  </div>

  <div>
    <h1>Exemple v-mode</h1>
    <p>Nom usuari: {{ nomUsuari }}</p>
    <input type="text" v-model="nomUsuari" placeholder="Escriu aqui el teu nom">
  </div>
  
  <div>
    <h1>Exemple v-for</h1>
    <ul>
      <li v-for="producte in productes" :key="producte.id">{{ producte.nom }}  -  {{ producte.preu }} €</li>
    </ul>
  </div>

  <div>
    <h1>Exemle v-if i v-else</h1>
    <p v-if="logat">Hola!!! ^-^</p>
    <p v-else="logat">Inicia sessio porfa n-n</p>
  </div>

  <div>
    <h1>Exemple v-show</h1>
    <button @click="mostrar=!mostrar">Mostrar</button>
    <p v-show="mostrar">n-n</p>
  </div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
