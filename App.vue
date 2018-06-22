<template>
  <view class="container">
    <text-input class="text-input-container"
        v-model="text"
      />
    <button v-bind:title="message" v-bind:on-press="handleBtnPress"/> 
    <text v-bind:key="item" v-for="item in list">{{item}}</text>
    </view>
</template>
 
<script>
export default {
  data: function() {
    return {
      text: '',
      message: 'Welcome!',
      list:[],
    };
  },
  methods: {
    handleBtnPress: function() {
      if (this.text != "clear"){
        alert("Hey! "+ this.text);
        this.list.push(this.text);
      } else {
        this.list = [];
      }
      this.text = '';
    }
  }
};
</script>

<style>
.container {
  background-color: white;
  flex: 1;
  margin-top: 30;
  align-self: auto;
  align-items: center;
}
.text-input-container {
  width: 300;
  height: 50;
  border-color: black;
}
</style>
