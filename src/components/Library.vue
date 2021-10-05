<template>
    <div class="library">
        <div class="container">
            <Album  v-for="(element, index) in filteredAlbi" :key="index" :album="element"/>
        </div>
    </div>
</template>

<script>
import Album from './Album.vue';
import axios from 'axios';

export default {
    name: 'Library',

    components: {
        Album
    },

    props: {
        genre: String,

        artist: String
    },

    data() {
        return {
            albi: [],

            genresList: []
        }
    },

    computed: {
        filteredAlbi() {
            if(this.artist != "" || this.genre != "") {
                const artistGenreFilter = this.albi.filter(album => {
                    if(album.author.toLowerCase().includes(this.artist.toLowerCase()) && album.genre.toLowerCase().includes(this.genre.toLowerCase())) {
                        return true
                    }
                });

                return artistGenreFilter;
            } else {
                return this.albi
            }
        }
    },

    created() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then( (response) => {
                this.albi = response.data.response;

                this.albi.forEach(album => {
                    if(!this.genresList.includes(album.genre)) {
                        this.genresList.push(album.genre)
                    }
                });

                this.$emit('getGenres', this.genresList);
            }
        )
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/common.scss';

    .library {
        background-color: #1E2D3B;
        padding-block: 5rem;
        height: calc(100vh - 70px);
        overflow-y: auto;

        .container {
            flex-wrap: wrap;
            min-width: 1100px;
        }
    }
</style>