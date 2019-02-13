<template id="contact">
    <div >
      <h3 v-bind:class='class_object'>Contact Section</h3>
       
         <p>{{prop}}</p> 
    
            <label>Your Name</label>
            <input v-model="name">
            <label>Your Message</label>
            <select v-model="option">
                <option v-for='element in option_type' v-bind:value='element.value' v-bind:key='element.key'>{{element.text}}</option>
            </select>
            <textarea v-model="message"></textarea>
            <button @click="sent=!sent">Submit</button>
           <Input/> 
     
        <p>Display</p>
        <p>{{name}}</p>
        <p>{{message}}</p>
        <p>{{option}}</p> 
      
        
    </div> 
 
       
</template>



<script>
    export default {
        name: "Contact",
        template: "#contact",
        data: function() {
            return {
                name: '',
                message: '',
                option: '',
                option_type: [
                    {value:'inquiry', text:'contact you about your website'},
                    {value: 'complaint', text:'contact you about a complaint'},
                    {value: 'feedback', text: 'contact you to give you some feedback'}
                ],
                sent: false,
                active: true
            }
        },
        props: ['prop'],
        filters:{
            capitalise:function(v){
             return v.toUpperCase()
            }
        },
        computed: {
            class_object: function(){
                 return {
                red_font: this.active
              }
            } 
        }
    }

  
</script>

 <style lang="scss" scoped>
$color: red;
.red_font{color:$color};

</style>

