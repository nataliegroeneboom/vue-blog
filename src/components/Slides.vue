<template>
<div class="slides" ref="app">
 <div v-bind:style="{width: innerWidth + 'px', marginLeft: '-'+ slidesInnerMarginLeft + 'px'}" class="slides-inner"> 
           
           <Slide v-for="slide in slides" v-bind:key="slide.key" v-bind:style="{width: singleWidth + 'px'}" v-bind:slide="slide" />
     </div>   
 <div class="navigation">
     <span v-on:click="goToPrev">Prev</span>
     <span class="nav-number" v-for="(slide, index) in slides" v-bind:key="index">{{index+1}}</span>
     <span v-on:click="goToNext">Next</span>
 </div>
</div>
</template>

<script>
import Slide from './Slide';
export default {
    data: function() {
        return {
            slides: [
                    {src: 'building'},
                    {src: 'work'},
                    {src: 'mountain'},  
            ],
            innerWidth: 0,
            singleWidth: 0,
            currentIndex: 0
           
        }
    },
    methods: {
        goToPrev(){
            if(this.currentIndex === 0){
                return
            }else{
                this.currentIndex--
            }
            
            
        },
        goToNext(){
            if(this.currentIndex === this.slides.length-1){
                return;
            }else{
                this.currentIndex++ 
            }
           
        }
    },
    computed: {
    slidesInnerMarginLeft () {
        return this.currentIndex * this.singleWidth
    }
    },
    props: {
        itemsPerSlide: {
            type: null,
            default: 1
        }
    },
    components: {
        Slide
    },
    mounted() {
        this.singleWidth = this.$refs.app.clientWidth/this.itemsPerSlide
        this.innerWidth = this.singleWidth*this.slides.length
    }
}
</script>

<style scoped>
.slides {
    width: 1500px;
    overflow: hidden;
    text-align: center;

}
.slides-inner {
     transition: margin 0.6s ease-out;
}
.nav-number{
    margin: 0 5px;
    background-color: white;
    padding: 0 5px;
    border: 1px solid black;
    cursor: pointer
}

</style>
