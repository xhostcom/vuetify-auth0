<template>
  <v-app>
    <v-app-bar
      app
      color="secondary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Logo"
          class="shrink mr-2"
          contain
          src="./assets/logo.png"
          transition="scale-transition"
          width="40"
        />

      </div>
       <v-spacer></v-spacer>
       <v-btn to="/">Home</v-btn>
       <v-btn to="/about">About</v-btn>
       <v-btn to="/contact" >Contact </v-btn>
       <v-btn to="/members">Members</v-btn>
      <v-btn @click="logOut">Logout</v-btn>
    </v-app-bar>
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
    clientId: process.env.VUE_APP_AUTH0_CONFIG_CLIENTID
  }
  },
  methods: {
    logOut() {
      console.log('Logging Out');
    }
  }
};
</script>
