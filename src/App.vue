<template>
  <v-app>
    <v-main>
      <router-view>
        <Register />
      </router-view>
    </v-main>
  </v-app>
</template>

<script>
import Register from "./views/Register";

export default {
  name: "App",

  components: {
    Register
  },

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Rubik:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,300;1,400&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Rubik", sans-serif;
}

ul,ol{
  padding-left: 0!important;
}

.primary-text{
  color: #fc913a;
}


/* Custom Theme */
.v-application {
  font-family: "Rubik", sans-serif;
}


</style>
