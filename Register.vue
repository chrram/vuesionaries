<template>
  <view class="container">
    <text class="text-color-primary">Vuesionaries</text>
    <text :style="{color: 'brown',margin:20,fontSize:20,fontWeight:'bold'}">Coffee Drinker 2000</text>

    <text 
    :style="{color: errorMsg ? 'red' : 'green', margin:0, fontSize:15, fontWeight:'bold'}">
      {{errorMsg || success}} 
    </text>

    <text-input
      v-model="email"
      placeholder="Your email"
      :style="{ height: 40, margin:10, width: 300, borderColor: 'gray', borderWidth: 1 }"
    />

    <text-input
      v-model="password"
      placeholder="Your password"
      :style="{ height: 40, margin:10, width: 300, borderColor: 'gray', borderWidth: 1 }"
    />

    <text-input
      v-model="password2"
      placeholder="Confirm your password"
      :style="{ height: 40, margin:10, width: 300, borderColor: 'gray', borderWidth: 1 }"
    />

    <touchable-opacity
      :on-press="register"
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
      <text :style="{ color: 'white' }">Register</text>
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
      email: "",
      password: "",
      password2: "",
      errorMsg: "",
      success: ""
    };
  },
  methods: {
    async register () {
    
      if (!/^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/.test(this.email)){
        return this.errorMsg = "It is not a good email."
      }

      if(this.password !== this.password2){
        return this.errorMsg = "The passwords are not matching eachother!"
      }

      this.errorMsg = ""
      this.success= "Successfully registered account!"
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
