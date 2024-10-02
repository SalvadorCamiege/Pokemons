<script setup>
import { onMounted, reactive, ref, computed } from "vue";
import ListPokemons from "../components/ListPokemons.vue"
import CardPokemonSelected from "../components/CardPokemonSelected.vue"


let urlBasepng = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/")
let pokemons = reactive(ref());
let searchPokemonField = ref("");/* utilizei esse combinação de comandos para criar a barra de pesquisa*/
let pokemonSelected = reactive(ref());
let loading = ref(false)

onMounted(() => {
    fetch("https://pokeapi.co/api/v2/pokemon?limit=150&offset=0")
        .then(res => res.json())
        .then(res => pokemons.value = res.results);
});

/* utilizei esse combinação de comandos para criar a barra de pesquisa que da a combinação perfeita*/
const pokemonFiltered = computed(() =>{
   if(pokemons.value && searchPokemonField.value){
        return pokemons.value.filter(pokemon=>
          pokemon.name.toLowerCase().includes(searchPokemonField.value.toLowerCase())
        ) 
   }
   return pokemons.value; /* returna com zero quando não se encontra os resultados obs: alterar com typescript depois de terminar o projecto*/
   })

   const selectPokemon = async (pokemon) =>{
      loading.value = true;
      await fetch(pokemon.url)
     .then(res => res.json())
     .then(res => pokemonSelected.value = res)
     .catch(err => alert(err))
     .finally(() =>loading.value = false)
     
     console.log(pokemonSelected.value);
} 
</script>


<template>
<main>
    <div class="conteiner text-body-secondary">
         <div class="row mt-5">
              <div class="col-sm-12 col-md-6">
                      <CardPokemonSelected
                       :nome="pokemonSelected?.name"
                       :xp="pokemonSelected?.base_experience"
                       :height="pokemonSelected?.height"
                       :img="pokemonSelected?.sprites.other.dream_world.front_default"
                       :loading="loading"

                      />  <!--importamos o card como verificamos aqui...-->
              </div>
              <div class="col-sm-12 col-md-6">
                   <div class="card cardList">
                    <div class="card-body row">
                      
                      <div class="mb-3">
                            <label hidden for="searchPokemonField" class="form-label">pesquisar</label>
                            
                            <input 
                            v-model="searchPokemonField" 
                             type="text" class="form-control" id="searchPokemon" placeholder="pesquisar">
                      </div>
                      
                      <ListPokemons 
                           v-for="pokemon in pokemonFiltered" 
                           :key="pokemon.name" 
                           :nome="pokemon.name"
                           :urlBasepng="urlBasepng + pokemon.url.split('/')[6] + '.png'"
                           @click="selectPokemon(pokemon)"
                      />
                    </div>
                   </div>
              </div>
            </div>
    </div>
    
</main>
</template>

<style scoped>
.cardList{
     max-height: 75vh;
     overflow-y: scroll;
     overflow-x: hidden;
}
</style>