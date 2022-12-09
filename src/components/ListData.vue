<template>
  
    <ul>
        <PersonData 
        v-for="(item,index) in employees" 
        :key="index"
        :id="index"
        :name="item.name"
        :salary="item.salary"
        :position="item.position"
        
         />   
    </ul>
    
    
  
</template>

<script>
import PersonData from './PersonData.vue'
export default {    
    name:"ListData",
    components: { 
        PersonData ,
    },
    props:["employees"],
//     data(){
//     return{
//         employees:[
//           {id:1, name:"AOM JANJEEN", salary:40000, position:"Programmer", isVisible:false},
//           {id:2, name:"KHOM JANJEEN", salary:32000, position:"Marketing", isVisible:false},
//           {id:3, name:"JAI JANJEEN", salary:20000, position:"Management", isVisible:false},
//           {id:4, name:"SAMAT JANJEEN", salary:20000, position:"Programmer", isVisible:false},
//           {id:5, name:"MEW JANJEEN", salary:29000, position:"Programmer", isVisible:false},
//           {id:6, name:"Test JANJEEN", position:"Assitant", isVisible:false}
//         ]
//     }
//   },
  methods:{
    
  }

}
</script>

<style scoped>
    ul{
        list-style: none;
        margin: 1rem 0;
        padding: 0;
    }
</style>