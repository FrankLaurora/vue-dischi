<template>
    <div class="library">
        <div class="container">
            <Album  v-for="(element, index) in albums" :key="index" :album="element"/>
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

    data() {
        return {
            albums:[]
        }
    },

    created() {
        axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then( (response) => {
                this.albums = response.data.response;
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

        .container {
            flex-wrap: wrap;
        }
    }
</style>