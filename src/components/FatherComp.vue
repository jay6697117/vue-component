<template>
  <div>
    <div>{{ counterObj.counter }}</div>
    <button @click="add">+</button>
    <button @click="sub">-</button>
    <br />
    <br />
    <SonComp />
  </div>
</template>

<script>
import SonComp from './SonComp';
export default {
  components: {
    SonComp
  },
  data() {
    return {
      title: 'FatherComp组件',
      counterObj: {
        counter: 0
      }
    };
  },
  provide() {
    return {
      nameObj: this.counterObj
    };
  },
  methods: {
    add() {
      this.counterObj.counter += 1;
    },
    sub() {
      this.counterObj.counter -= 1;
    }
  },
  mounted() {
    console.log('FatherComp this :>> ', this);
    console.log('FatherComp this.$options.data :>> ', this.$options.data);
    console.log('FatherComp this.$options.provide :>> ', this.$options.provide);
  }
};
</script>

<style lang="less" scoped></style>
