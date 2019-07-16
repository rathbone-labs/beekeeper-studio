<template>
  <v-app>
    <TabbedView :connection="connection"></TabbedView>
  </v-app>
</template>

<script>
import TabbedView from './components/TabbedView.vue'

export default {
  name: 'App',
  components: {
    TabbedView
  },
  data () {
    return {
      connection: ""
    }
  }
}
</script>
