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
    height: 3.75rem;

    img{
        margin-left: 20px;
        object-fit: contain;
        height: 100%;
        width: 3.5rem;
    }


}
</style>