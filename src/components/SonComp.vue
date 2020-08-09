<template>
  <div class="son-comp-style">
    <div>SonComp: {{ nameObj.counter }}</div>
    <div>SonComp nameObj: {{ nameObj }}</div>
    <button @click="add">+</button>
    <button @click="sub">-</button>
  </div>
</template>

<script>
export default {
  inject: ['nameObj'],
  data() {
    return {
      title: 'SonComp组件'
    };
  },
  methods: {
    add() {
      this.nameObj.counter += 1;
    },
    sub() {
      this.nameObj.counter -= 1;
    }
  },
  mounted() {
    console.log('SonComp this :>> ', this);
    console.log('SonComp this.nameObj :>> ', this.nameObj);
    console.log('SonComp this.$options.data :>> ', this.$options.data);
    console.log('SonComp this.$options.provide :>> ', this.$options.provide);

  }
};
</script>

<style lang="less" scoped>
.son-comp-style {
  font-size: 30px;
  color: blue;
  background-color: #ccc;
}
</style>
