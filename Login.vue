<template>
  <view class="container">
    <text class="text-color-primary">Vuesionaries</text>
    <text :style="{color: 'brown',margin:20,fontSize:20,fontWeight:'bold'}">Coffee Drinker 2000</text>
    <text-input
      v-model="email"
      :style="{ height: 40, width: 300, borderColor: 'gray', borderWidth: 1 }"
    />

    <text-input
      v-model="password"
      :style="{ height: 40, width: 300, borderColor: 'gray', borderWidth: 1 }"
    />

    <touchable-opacity
      :on-press="login"
      :style="{
        width: 200,
        height: 40,
        margin: 20,
        backgroundColor: 'brown',
        alignItems: 'center',
        justifyContent: 'center',
        borderRadius:10,
      }"
    >
      <text :style="{ color: 'white' }">Login</text>
    </touchable-opacity>


    <touchable-opacity
      :on-press="() => navigation.navigate('Register')"
      :style="{
        height: 40,
        margin: 10,
        backgroundColor: 'transparent',
        alignItems: 'center',
        justifyContent: 'center',
      }"
    >
      <text :style="{color: 'brown',margin:10,fontSize:15,fontWeight:'bold'}">Dont have an account yet? Register here!</text>
    </touchable-opacity>


    
  </view>
</template>

<script>
export default {
  props: {
    navigation: {
      type: Object,
    },
  },

  data() {
    return {
      email: "email@gmail.com",
      password: "password213",
      errorMsg: "",
    };
  },
  methods: {
    async login () {
      console.log("Login here")
    }
  },

  mounted() {},
};
</script>


<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: brown;
  font-size:30;
  font-weight:bold;
}
</style>
