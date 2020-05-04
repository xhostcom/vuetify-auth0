<template>
  <v-app>
    <v-toolbar app
    color="green lighten-6"
    >
    <v-toolbar-title class="headline text-uppercase">
     <span>Vuetify Auth0</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn to="/" class="mr-2">Home</v-btn>
      <v-btn to="/about" class="mr-2">About</v-btn>
      <v-btn to="/contact" class="mr-2">Contact</v-btn>
      <v-btn to="/members" class="mr-2">Members</v-btn>
      <v-btn @click="logout" v-if="this.$store.state.userIsAuthorized">Logout</v-btn>
    </v-toolbar>
    <v-content>
      <router-view></router-view>
    </v-content>
   </v-app>
</template>
<script>
export default {
  name: 'App',
  data () {
    return {
      clientId: process.env.VUE_APP_AUTH0_CONFIG_DOMAIN
    }
  },
  methods:{
    logout(){
      this.$store.dispatch('auth0Logout');
      console.log('logging out');
    }
  },
  beforeCreate(){

  }
}
</script>
