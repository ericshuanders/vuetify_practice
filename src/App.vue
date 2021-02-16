<template>
  <v-app>
    <v-card width="400" class="mx-auto mt-10">
      <!-- mx is margin on both sides, mt is margin top -->
      <v-card-title>
         <h1>Login</h1>
      </v-card-title>
      <v-card-text>
        <v-form>
          <v-text-field prepend-icon="mdi-account-circle" label="Username"/>
          <!-- prepend-icon puts md icon at beginning -->
          <v-text-field prepend-icon="mdi-lock" :append-icon="showPassword? 'mdi-eye-off': 'mdi-eye'" :type="showPassword? 'password': 'text'" label="Password" @click:append="showPassword=!showPassword"/>
          <!-- Bind type to make the type dynamic, able to switch between 'password' and 'text' -->
          <!-- @click:append toggles the data, so when a user clicks, the showPassword will flip boolean value which in turn changes the type -->
          <v-divider/>
          <v-card-actions>
            <v-btn color="success">Register</v-btn>
            <v-spacer/>
            <v-btn color="info">Login</v-btn>
          </v-card-actions>
        </v-form>
      </v-card-text>
     
    </v-card>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    // HelloWorld,
  },

  data: () => ({
    showPassword: true
  }),
};
</script>
