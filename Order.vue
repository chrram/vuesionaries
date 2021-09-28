<template>
  <view class="container">
    <text class="text-color-primary">Vuesionaries</text>
    <text :style="{color: 'brown',margin:20,fontSize:20,fontWeight:'bold'}">Coffee Drinker 2000</text>

    <touchable-opacity
      :on-press="() => {}"
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
      <text :style="{ color: 'white' }">Order</text>
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

    };
  },
  methods: {

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
