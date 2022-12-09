<template>
  <CardItem>
    <template v-slot:card-header>
        <h2>{{name}} </h2>
    </template>
    
  </CardItem>
</template>

<script>
import CardItem from './CardItem.vue'
export default {
  components: { CardItem },    
    name:"PersonData",    
    data(){
        return{
            message:"Person Data"
        }
    },
    props:{
        id:{
            type:Number
        },
        name:{
            type:String,
            requirde:true
        },
        salary:{
            type:Number,
            default:15000
        },
        position:{
            type:String,
            requirde:true

        },
        isVisible:{
            type:Boolean,
            requirde:true

        }
    },
    methods:{
        
    }
}
</script>

<style scoped>
    h2{
        color: whitesmoke;
    }
    
    button{
        font:inherit;
        cursor: pointer;
        border: 1px solid #f78f78;
        background: #f78f78;
        color: whitesmoke;
        padding:.5rem 1rem ;
        box-shadow: 1px 1px 2px #000000;
        border-radius: 50px;
        margin-bottom: 2%;
    }
    button:hover{
        border: 1px solid #f78555;
        background: #f78555;
        transition: all .3s;
    }
    .fade-enter-from{
        opacity: 0;
    }
    .fade-enter-active{
        transition: all .5s linear;
    }
</style>