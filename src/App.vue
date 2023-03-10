<template>
  <v-app>
    <v-content>
        <v-layout>
          <v-container v-if='showLogin' v-on:login = "showLogin = false">
            <TitleBarComponent v-on:login="loginFalse" />
          </v-container>
          <v-container v-if='!showLogin'>
            <DatePickerComponent/>
          </v-container>

        </v-layout>
    </v-content>
  </v-app>
</template>

<script>
import DatePickerComponent from './components/DatePickerComponent'
import TitleBarComponent from './components/TitleBarComponent'

export default {
  name: 'App',
  components: {
    TitleBarComponent,
    DatePickerComponent
  },
  data () {
    return {
      showLogin:true,
      //
    }
  },
  methods : {
    loginFalse : function name() {
      //alert('login!');
      this.showLogin =false
    }
  }
}
</script>
