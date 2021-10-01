<template>
    <div class="card">
        <img :src="album.poster" :alt="album.title">
        <h3>{{album.title}}</h3>
        <div class="album_info">{{album.author}}</div>
        <div class="album_info">{{album.year}}</div>
    </div>
</template>

<script>
export default {
    name: 'Album',

    props: {
        album: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/variables.scss';

    .card {
        width: calc(20% - 40px);
        margin-inline: 20px;
        margin-block: 10px;
        padding: 20px;
        background-color: $secondary-color;
        text-align: center;

        img {
            width: 100%;
        }

        h3 {
            text-transform: uppercase;
            font-size: 18px;
            margin-block: 1.1rem;
        }

        .album_info {
            color: $tertiary-color;
            font-size: small;
        }
    }

</style>