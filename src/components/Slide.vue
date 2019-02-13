<template>
    <div class="slideshow">
      <div class ="background" :class='slide.src'>hello</div>
        <About v-bind:slide="slide" />
        </div>
</template>

<script>
import About from './About';
export default {
    data: function(){
        return {}
    },
    props: ['slide'],
    components: {
        About
    }
}
</script>

<style scoped>
.background{
    height: 100px;
}
.building{
   background-image: url('~@/assets/img/building.jpg');
    height: 500px;
    width: 100%;
    background-size: cover;
}
.work {
    background-image: url('~@/assets/img/work.jpg');
    height: 500px;
     width: 100%;
    background-size: cover; 
}
.mountain {
    background-image: url('~@/assets/img/mountain.jpg');
    height: 500px;
     width: 100%;
    background-size: cover; 
}
.slideshow{
    display: inline-block
}
</style>

