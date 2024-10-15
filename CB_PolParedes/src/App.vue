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
