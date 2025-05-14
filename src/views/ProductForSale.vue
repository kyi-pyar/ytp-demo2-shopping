<template>
  <v-container>
 <v-row class="text-center">
   <v-col cols="12">
    <h1>Products for Sale</h1>      
   
    <div style="background-color: #AA5733; color: white;">{{ order}}</div>      
   </v-col>
 </v-row>  
 <v-row >
   <v-col cols="6" v-for="product in products" :key="product.id">
     <ForEachProductView :pp="product"
     @event-like-click="likeCount"
     @event-cart-click="AddToCart"
     >
      <template #name>
        <div style="color:red;">{{ product.name }}</div>
      </template>
      <template #price>
         <div v-if="product.dis" style="color:blue;text-decoration: line-through;">Price: {{ product.price }}</div>
        <div v-else style="color:blue;">Price: {{ product.price }}</div>
        <div v-if="product.dis">Discount ({{ product.dis }}%) :  {{ product.price - (product.price*product.dis/100) }}</div>
      </template>
      <template #like>
         <v-btn color="orange" prepend-icon="mdi-thumb-up" >{{ product.like }}</v-btn>  
      </template>
      <template #cart>
         <v-btn color="orange" :disabled="product.flag" prepend-icon="mdi-cart-arrow-down"></v-btn>
      </template>
     </ForEachProductView>
   </v-col>
 </v-row>
 
</v-container>    
</template>
<script>
import { mapActions } from 'vuex';
import ForEachProductView from './ForEachProductView.vue';


export default {
 components:{ForEachProductView},
  data: () => ({  
     order:"",     
     products:[
     {id:1,like: 0, flag:false,name:"Panda",src:"https://ataacars.com/12330-medium_default/xl-panda-link-teddy-bear.jpg",price:15000,size:"1\"-2'", description:"(Panda)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
     {id:2,like: 0, flag:false,dis:10,name:"Churkey",src:"https://wallpapers.com/images/high/scary-chucky-png-58-tz7gcu5cfdr1mbcp.png",price:25000,size:"3\"-2'", description:"(Charkey)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
     {id:3,like: 0, flag:false,name:"Dog",src:"https://c8.alamy.com/comp/BHBB5H/dog-doggy-poppy-stuffed-soft-toy-doll-childhood-children-decoration-BHBB5H.jpg",price:5000,size:"1\"-2'", description:"(Dog)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
     {id:4,like: 0, flag:false,dis:5,name:"Cat",src:"https://img.fruugo.com/product/7/94/756538947_0340_0340.jpg",price:5000,size:"1\"-2'", description:"(Cat)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"},
     {id:5,like: 0, flag:false,name:"Cindralla",src:"https://www.youloveit.com/uploads/posts/2025-04/medium/1745130109_youloveit_com_disney_princess_cinderella_birthday_celebration_doll.jpg",price:50000,size:"1\"-2'", description:"(Cindralla)Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, est alias, incidunt consectetur culpa eveniet itaque eius voluptates rerum a odit cupiditate tenetur velit sunt. Laudantium odit iste consectetur recusandae!"}
     ]
 }),
 methods:{  
  
  ...mapActions(['AddToCart']),

  likeCount(pp){
    pp.like++
  },
  // AddToCart(pp){     
  //   pp.flag=!pp.flag 

  // }
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

