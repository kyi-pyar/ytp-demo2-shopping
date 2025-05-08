<template>
     <v-container>
    <v-row class="text-center">
      <v-col cols="12">
       <h1>Products for Sale</h1>   
       {{ order}}
       <ForEachProductView/>
      </v-col>
    </v-row>  
    
    
  </v-container>    
</template>
<script>
import ForEachProductView from './ForEachProductView.vue';



export default {
    components:{ForEachProductView},
     data: () => ({  
        order:"",
        products:[{id:1,name:"Panda",src:"https://ataacars.com/12330-medium_default/xl-panda-link-teddy-bear.jpg",price:15000,size:"1\"-2'", description:"(Panda)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
        {id:2,name:"Charkey",src:"",price:25000,size:"3\"-2'", description:"(Charkey)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
        {id:3,name:"Dog",src:"",price:5000,size:"1\"-2'", description:"(Dog)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
        {id:4,name:"Cat",src:"",price:5000,size:"1\"-2'", description:"(Cat)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
        {id:5,name:"Cindralla",src:"",price:50000,size:"1\"-2'", description:"(Cindralla)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"}

        ]
    }),
    methods:{  
    },
   async created(){        
        await new Promise(resolve =>
        setTimeout(()=>{
         this.order=("You can order now!"); resolve();
        },5000)
        )
        
    } 
}
</script>

