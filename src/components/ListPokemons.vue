<script setup>
     const pokemon = defineProps(["nome", "urlBasepng"])
</script>


<template>
     <div class="col-4">
          <div class="card p-2 mb-3 cardListPokemon">
                <p class="text-center">{{ pokemon.nome }}</p>
                <img 
                    :src="urlBasepng" class="card-img-top" 
                    alt="..."
                />
          </div>
     </div>
</template>

<style scoped>
.cardListPokemon{
    background: rgb(2,0,36);
    background: linear-gradient(90deg, rgba(2,0,36,5) 0%, rgba(70,113,252,0.4) 37%, rgba(0,212,255,1) 100%);
    cursor: pointer;
}

.cardListPokemon:hover{
    background: rgb(2,0,36);
    background: linear-gradient(90deg, rgba(2,0,36,3) 0%, rgba(70,113,252,0.2) 37%, rgba(0,212,255,1) 100%);
    cursor: pointer;
}

</style>