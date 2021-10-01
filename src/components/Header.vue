<template>
    <header>
        <img :src="image" alt="logo">
    </header>
</template>

<script>
export default {
    name: 'Header',

    props: ['image']
}
</script>

<style lang="scss" scoped>
    header {
        background-color: #2E3A46;

        img {
            width: 3rem;
            margin-inline: 22px;
            margin-block: 11px;
        }
    }
</style>