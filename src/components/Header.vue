<template>
    <header class="text-start px-2 py-2">
        <img :src="image" :alt="title">
    </header>
</template>

<script>
export default {
    name:'Header',
    props:['image','title'],
}
</script>

<style lang="scss" scope>

@import '../assets/style/variables.scss';

header{
    width: 100%;
    background-color: $header_background_color;
    img{
        object-fit: contain;
        height: 100%;
        width: 2.5rem;
    }


}
</style>