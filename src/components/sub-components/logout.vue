<template lang="html">
  <v-card flat>
    <v-toolbar color="primary" dark dense flat>
      <v-toolbar-title>
        <v-icon left>fas fa-question-circle</i></v-icon>
        Are you sure you want to sign out?
      </v-toolbar-title>
    </v-toolbar>
    <v-card-text>
      <v-layout row wrap align-center justify-space-around>
          <v-btn color="secondary" @click="signOut()" round outline>
            <v-icon left>fas fa-check</v-icon>
            Sign out
          </v-btn>
          <v-btn color="red darken-4" dark @click="deactivateSignOut()" round outline>
            <v-icon left>fas fa-times</v-icon>
            Cancel
          </v-btn>
      </v-layout>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data(){
    return{
      usr : "",
      pass: "",
      showPass: false
    }
  },
  methods: {
    signOut(){
      this.$store.dispatch('signOut')
    },
    deactivateSignOut(){
      this.$store.dispatch('activateSignOut', false)
    }
  }
}
</script>

<style lang="css">
</style>
