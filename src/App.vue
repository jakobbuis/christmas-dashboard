<template>
    <div id="app">
        <nav class="navbar is-danger">
            <div class="navbar-brand">
                <h1 class="navbar-item">
                    Instant-sfeer-generator 3000
                </h1>
            </div>
        </nav>

        <div class="container">
            <div class="columns" v-for="set in songs">
                <song v-for="song in set" :key="song.id" :song="song" @play="startPlaying"></song>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import Song from './components/Song.vue';

export default {
    name: 'app',
    components: {Song},
    data() {
        return {
            songs: [
                [
                {"title": "Sfeer I", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "normal"},
                {"title": "Sfeer II", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "normal"},
                {"title": "Sfeer III", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "normal"},
                ],
                [
                {"title": "Sfeer IV", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "normal"},
                {"title": "Sfeer V", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "normal"},
                {"title": "Sfeer VI", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "normal"},
                ],
                [
                {"title": "Meer sfeer!", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "excessive"},
                {"title": "MAXIMALE sfeer!!", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "excessive"},
                {"title": "SFEER OVERLOAD!!!1", "id": "4Np5xnWc3vYfosnB6xlsTo", "type": "excessive"},
                ],
            ],
        };
    },

    methods: {
        startPlaying(id) {
            this.command('isolate');
            this.command('volume/40');
            this.command(`spotify/now/spotify:track:${id}`);
        },

        command(command) {
            const zone = 'Discotheek';
            axios.get(`http://192.168.20.108:5005/${zone}/${command}`);
        }
    },
}
</script>

<style lang="scss">
@import './node_modules/bulma/bulma.sass';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
    margin-top: 1em;
}

h1 {
    margin: 0 auto;
}
</style>
