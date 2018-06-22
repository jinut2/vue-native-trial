<template>
  <view class="container">
    <text-input class="text-input-container"
        v-model="text"
      />
    <button 
      color="green"
      accessibility-label="Greet the User"
      v-bind:title="message" 
      v-bind:on-press="welcomeBtnPress"
    />
    <status-bar
      background-color="blue"
      bar-style="light-content"
    />
    <button 
      title="clear" 
      v-bind:on-press="clearBtnPress"
    />
    <scroll-view>
      <text v-bind:key="item" v-for="item in list">{{item}}</text>
    </scroll-view>
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
    welcomeBtnPress: function() {
      if (this.text != "clear"){
        alert("Hey! "+ this.text);
        this.list.push(this.text);
      } else {
        this.list = [];
      }
      this.text = '';
    },
    clearBtnPress: function() {
        this.list = [];
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
  align-items:center;
}
.text-input-container {
  width: 300;
  height: 50;
  border-color: black;
}
</style>
