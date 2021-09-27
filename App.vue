<template>
  <app-navigator></app-navigator>
</template>

<script>
import {
  createAppContainer,
  createStackNavigator,
} from "vue-native-router";

import * as firebase from "firebase";
import LoginScreen from "./Login.vue"
import RegisterScreen from "./Register.vue"

import { LogBox } from 'react-native';

LogBox.ignoreLogs(['Warning: ...']);

// RN >= 0.52
import {YellowBox} from 'react-native';

YellowBox.ignoreWarnings(['Warning: ReactNative.createElement']);

// RN < 0.52
console.ignoredYellowBox = ['Warning: ReactNative.createElement'];


const StackNavigator = createStackNavigator(
  {
    Home: LoginScreen,
    Register: RegisterScreen,
  },
  {
    initialRouteName: 'Home',
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator },
  

  data() {
    return {
      userInfo: {}, 
    };
  },

  async mounted () {

  },

}
</script>