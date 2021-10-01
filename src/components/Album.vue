<template>
    <section class="album">
        <img  src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
        <div class="albums-text">
            <h3>New Jersey</h3>
            <h4>Bon Jovi</h4>
            <h6>1988</h6>
        </div>
    </section>
    
</template>

<script>

export default {
    name:'Album',
    props:[]
    
}
</script>

<style lang="scss" scope>
@import '../assets/style/variables.scss';


.album{
    background-color: $album_background_color;
    width: calc(100% / 5 - 2.50rem);
    margin: .625rem 1.25rem;
    text-align: center;
    img{
        padding: .125rem;
        object-fit: contain;
        width: 100%;
    }


    .albums-text{

        h3{
            font-size: 20px;
            color: $primary_album_h3_color;
        }
        h4,h6{
            font-size: .875rem;
            color: $secondary_album_text_color;
        }
    }
}
</style>