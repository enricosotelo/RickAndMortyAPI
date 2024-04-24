<script>
import {
    onMounted,
    reactive,
    ref
} from 'vue';
import axios from 'axios'

export default {
    name: 'app',
    components: {},
    data() {
        return {
            characters: null
        }
    },
    mounted() {
        this.getTodos();
    },
    methods: {
        getTodos() {
            axios
                .get('https://rickandmortyapi.com/api/character/')
                .then(res => {
                    (this.characters = res.data.results)
                })
                .catch(e => {
                    console.log(e)
                })
                .then(res2 => {
                    (this.characters = res2.data.location)
                })
                .then(res3 => {
                    (this.characters = res3.data.episode)
                })
        }
    },

}
</script>

<template>
    <main>
        <div class="row">
            <div class="col-md-6" v-for="character in characters" :key="character.id">
                <div class="card mb-3" style="max-width: 540px;">
                    <div class="row g-0 p-2 ">
                        <div class="col-md-4">
                            <img :src="character.image" class="card-img-top" height="100%" alt="...">
                        </div>
                        <div class="col-md-8">
                            <div class="card-body">
                                <h5 class="card-title">{{character.id}}</h5>
                                <h5 class="card-title">{{ character.name }}</h5>
                                <p class="card-text">Status: {{ character.status }}</p>
                                <p class="card-text">Species: {{ character.species }}</p> 
                                <p class="card-text">Last known location: {{ character.location.name }}</p>
                                <p class="card-text">First seen: {{character.origin.name }}</p>
                                <p class="card-text"><small class="text-body-secondary">Gender: {{ character.gender }}</small></p>
    
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

