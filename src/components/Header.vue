<template>
    <header >
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
    display: flex;
    justify-content: flex-start;
    background-color: $header_background_color;
    width: 100%;
    height: 3.75rem;

    img{
        margin-left: 1.25rem;
        object-fit: contain;
        width: 3.5rem;
    }


}
</style>