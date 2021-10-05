<template>
    <header>
        <img :src="image" alt="logo">
        <form>
            <input type="text" v-model="searchInput" placeholder="Cerca un artista" @keyup.enter.prevent="$emit('searchByArtist', searchInput)">
            <button @click.prevent="$emit('searchByArtist', searchInput)">Cerca</button>
            <select name="genre_filter" id="genre_filter" v-model="selected_genre" @change="$emit('genreFilter', selected_genre)">
                <option value="" selected>Seleziona un genere</option>
                <option v-for="(genre, index) in genres" :key="index" :value="genre">{{genre}}</option>
            </select>

        </form>
    </header>
</template>

<script>
export default {
    name: 'Header',

    props: ['image', 'genres'],

    data() {
        return {
            selected_genre: "",

            searchInput: ""
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/variables.scss';

    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 70px;
        background-color: $secondary-color;
        padding-inline: 22px;

        img {
            width: 3.5rem;
        }

        select, input, button {
            padding: 0.5rem 1rem;
            border-radius: 5px;
            border: none;
            font-size: 1rem;
            font-weight: bold;
            outline: none;
        }

        input, button {
            margin-right: 1rem;
        }

        button {
            background-color: #2abe59;
            color: $secondary-color;
        }
    }
</style>