<template>
  <v-app>
    <!-- This app prop resizes the bar for the size of the component it's in -->
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text rounded>Home</v-btn>
      <v-btn text rounded>Login</v-btn>
    </v-app-bar>
    <v-main>
    <!-- Login Module -->
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
    </v-main>

  <v-footer
    color="primary lighten-1"
    padless
  >
    <v-row
      justify="center"
      no-gutters
    >
    <!-- “text” makes the background transparent
	“rounded” puts a large border radius on the button. If background is transparent, this is only visible on hover. -->
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
      >
        {{ link }}
      </v-btn>
      <v-col
        class="primary lighten-2 py-4 text-center white--text"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Vuetify Dashboard</strong>
      </v-col>
    </v-row>
  </v-footer>

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
    showPassword: true,
    links: ['Home', 'Login']
  }),
};
</script>
