
<template>
  <v-app>
    <v-app-bar
      app
      color="dark"
      dark
    >
        
    <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>loggedInPlayer</v-toolbar-title>

    <v-spacer></v-spacer> 
    
    
    <router-link to="/signup">
      <v-btn>SignUp</v-btn>
    </router-link>
    </v-app-bar>
      
    <v-navigation-drawer
      v-model="drawer"
      app
      dark
    >
      <v-list dense>
          
        <router-link to="/">
            <v-list-item link>
              <v-list-item-action>
                <v-icon>mdi-account</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>Profile</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
        </router-link>
        
          
        <router-link to="/">
            <v-list-item link>
              <v-list-item-action>
                <v-icon>mdi-gamepad-square-outline</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>Your Games</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
        </router-link>
          
        <router-link to="/">
            <v-list-item link>
              <v-list-item-action>
                <v-icon>mdi-rotate-3d-variant</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>Switch Game</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
        </router-link>
          
        <router-link to="/about">
            <v-list-item link>
              <v-list-item-action>
                <v-icon>mdi-map-marker-question-outline</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title>About App</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
        </router-link>
          
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-logout</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Log Out</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
          
      </v-list>
    </v-navigation-drawer>
      

    <v-content class="ma-6">
        <div id="app">
            <div id="nav">
                <router-link to="/">Home</router-link> |
                <router-link to="/currentgame">Current Game</router-link>
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
      drawer: null
  }),
};
</script>

<style>
    
    a{
        text-decoration: none
    }

</style>
