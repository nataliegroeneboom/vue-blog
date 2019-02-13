<template >
<div class="about">
  <h3>About Section</h3> 
  <p>{{currentPage}}</p>
  <div v-if="isActive">Show me for building
    
  </div>
</div>
</template>

<script>
export default {
    name: "About",
    props: ['slide'],
    data(){
      return{
        currentPage: this.slide.src,
        active: false
      }
    },
   computed: {
     isActive: function(){
       if(this.currentPage ==='building'){
         return true;
       }
       return false;
     }
   }
   
}
</script>