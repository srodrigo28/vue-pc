<template>
  <v-app>
    <app-menu />
    <app-toolbar />
    <v-main>
      <app-carrosel />
    </v-main>
    <app-footer />
  </v-app>
</template>

<script>
import Toolbar from './components/Toolbar.vue'
import Menu from './components/Menu.vue'
import Carrosel from './components/Carrosel.vue'
import Footer from './components/Footer.vue'
export default {
  components:{
    'app-toolbar': Toolbar,
    'app-menu': Menu,
    'app-carrosel': Carrosel,
    'app-footer': Footer
  },
}

</script>
