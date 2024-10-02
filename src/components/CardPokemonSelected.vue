<script setup>
const pokemon = defineProps(["nome", "xp", "height", "img", "loading"])
</script>

<template>
    <div class="card cardPokemonSelected" :class="loading ? '' : 'animate__animated animate__bounce'">
        <img v-if="pokemon.nome" :src="pokemon.img" class="card-img-top pt-2" :alt="pokemon.nome">

        <img v-else src="../assets/egg_pokemon.svg"  class="card-img-top pt-2" alt="???">
            <div class="card-body pt-2">
                <h5 class="card-title text-center">{{ pokemon.nome || '???' }}</h5>
                <hr>
                <div class="row text-center mt-3">
                      <section class="col">
                            <strong>xp:</strong>
                            <span>{{pokemon.xp }}</span>
                      </section>

                      <section class="col">
                            <strong>Altura:</strong>
                            <span>{{ pokemon.height }}</span>
                      </section>
                      
                </div>
                
                <div class="d-none d-md-block">
                    <div class="row text-center mt-4">
                      <section class="col">
                            <strong>xp:</strong>
                            <span>{{pokemon.xp }}</span>
                      </section>

                      <section class="col">
                            <strong>Altura:</strong>
                            <span>{{ pokemon.height }}</span>
                      </section>
                      
                    </div>
                </div>
                
                
            </div>
    </div>

</template>

<style scoped>
.cardPokemonSelected{
    height: 75vh;
    background: rgb(72, 76, 251);
    background: linear-gradient(90deg, rgba(2,0,36,5) 0%, rgba(244, 20, 20) 37%, rgb(235, 109, 6) 100%);
}

.cardPokemonSelected img{
    height: 250px;
}

@media (max-width:768px) {
    .cardPokemonSelected{
        height: 45vh;
        width: 50%;
        margin: 0 auto 10px auto;
    }

    .cardPokemonSelected img{
        height: 150px;
    }
}
</style>