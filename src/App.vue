
<template>
  <v-app>
    <v-app-bar
      app
      color="dark"
      dark
    >
    

        
    </v-app-bar>
      

    <v-content class="ma-6">
        <div id="app">
            <div id="nav">
                <router-link to="/">Home</router-link> |
                <router-link to="/about">About</router-link> |
                <router-link to="/playground">Playground</router-link>
                </div>
                <router-view/>
            </div>
    </v-content>
      
      
  </v-app>
</template>

<script>

export default {
  name: 'App',

  components: {
 
  },

  data: () => ({
    //
  }),
};
</script>
