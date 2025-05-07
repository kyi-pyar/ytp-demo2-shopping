<template>
  <v-app>  
      <v-app-bar height="50" width="90%" color="primary">
        <router-link to="/" >Home</router-link>
        <v-spacer></v-spacer>
        <router-link to="/about" >About</router-link>
      </v-app-bar>
      <v-main>
        <router-view/>
    </v-main>  
  </v-app>


</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
}
</script>
