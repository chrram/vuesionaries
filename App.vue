<template>
  <view class="container">
    <text class="text-color-primary">Vuesionaries</text>
    <text
      :style="{color: 'brown', margin: 20, fontSize: 20, fontWeight: 'bold'}"
      >Coffee Drinker 2000</text
    >
    <touchable-opacity
      :on-press="orderCoffee"
      :style="{
        width: 200,
        height: 40,
        margin: 20,
        backgroundColor: 'brown',
        alignItems: 'center',
        justifyContent: 'center',
        borderRadius: 10,
      }"
    >
      <text :style="{color: 'white'}">Order</text>
    </touchable-opacity>
    <touchable-opacity
      :on-press="resetCoffees"
      :style="{
        width: 200,
        height: 40,
        margin: 20,
        backgroundColor: 'brown',
        alignItems: 'center',
        justifyContent: 'center',
        borderRadius: 10,
      }"
    >
      <text :style="{color: 'white'}">Reset Order</text>
    </touchable-opacity>
  </view>
</template>

<script>
import firebase from 'firebase';
import {LogBox} from 'react-native';
import {Alert} from 'react-native';

LogBox.ignoreLogs(['Warning: ...']);

// Initialize Firebase
const firebaseConfig = {
  apiKey: 'AIzaSyD1peEn0FDGojiMbhTl-Y-uIuSSQL_XH2s',
  authDomain: 'mwsd-project-3b871.firebaseapp.com',
  projectId: 'mwsd-project-3b871',
  storageBucket: 'mwsd-project-3b871.appspot.com',
  messagingSenderId: '888827003326',
  appId: '1:888827003326:web:4d218192bd4ca25e2fb9ef',
};
const app = firebase.initializeApp(firebaseConfig);
export default {
  methods: {
    orderCoffee() {
      dbRef = firebase.default.firestore().collection('coffees');
      dbRef
        .doc('9IpwtC8Qh1jrlJ3STbrP')
        .set(
          {numberOrdered: firebase.firestore.FieldValue.increment(1)},
          {merge: true}
        )
        .then(() => {
          console.log('Ordered!');
          Alert.alert(
            'We received your order.',
            'Your coffee is on the way :)'
          );
        });
    },
    resetCoffees() {
      dbRef = firebase.default.firestore().collection('coffees');
      dbRef
        .doc('9IpwtC8Qh1jrlJ3STbrP')
        .set({numberOrdered: 0}, {merge: true})
        .then(() => {
          console.log('Reset coffee order!');
          Alert.alert(
            'We have reset your order.',
            'Hope to see you again soon.'
          );
        });
    },
  },
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
  font-size: 30;
  font-weight: bold;
}
</style>
