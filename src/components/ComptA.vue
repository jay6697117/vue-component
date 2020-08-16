<template>
  <h4>
    A组件:{{ msg }}
    <!--定义任意事件-->
    <button @click="brother">A组件传B组件</button>
  </h4>
</template>

<script>
//引入bus文件
import bus from '../utils/bus.js';
export default {
  data() {
    return {
      msg: '泰勒.斯威夫特',
      counter: 0
    };
  },
  methods: {
    brother() {
      //派发事件
      this.counter += 1;
      bus.$emit('eventA', this.msg + ' -- ' + this.counter);
    }
  }
};
</script>

<style lang="less" scoped></style>
