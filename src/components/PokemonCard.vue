<template>
    <div class="pokemon-card">
        <img :src="pokemon.image" :class="{ hidden: pokemon.discovered }">
        <div v-if="!pokemon.discovered">
            <input v-model="guessPokemon" @keyup.enter="checknamePokemon" type="text" placeholder="Adivina el Pokemón">
            <button @click="checknamePokemon">Descubrir</button>
        </div>
        <p v-else>{{ pokemon.name }}</p>
    </div>
</template>

<script>
export default {
    props: ['pokemon'],
    data() {
        return {
            guessPokemon: ''
        }
    },
    methods: {
        checknamePokemon() {
            if (this.guessPokemon.toLowerCase() === this.pokemon.name.toLowerCase()) {
                this.pokemon.discovered = true;
                this.$emit('discovered');
            } else {
                alert('Lo siento, ese no es el Pokémon!');
            }
            this.guessPokemon = '';
        }
    }
}
</script>

<style scoped>
.pokemon-card {
    margin: 10px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 10px;
    width: 150px;
    text-align: center;
    background: #FAEF9B;
    color: #0B2F9F;
}

img {
    width: 100%;
    filter: blur(5px) grayscale(100%); 
    transition: filter 0.5s;
}

img.hidden {
    filter: none;
}
</style>