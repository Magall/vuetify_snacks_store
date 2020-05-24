<template>
  <v-app>
    <Header />
    <v-content class="mx-4 mb-4" align="center" >
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
//import Header from './components/Header'
export default {
  name: "App",
  components:{
    Header: () =>import ('./components/Header.vue')
  },
  data: () => ({
    //
  })
};
</script>
