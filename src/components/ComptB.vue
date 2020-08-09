<template>
  <h2 style="color:red;">B组件:{{ msg }}</h2>
</template>

<script>
//引入bus文件
import bus from '../utils/bus.js';
export default {
  data() {
    return {
      msg: '默认内容'
    };
  },
  created() {
    //      监听派发的事件
    bus.$on('eventA', res => {
      console.log('res :>> ', res);
      this.msg = res;
    });
  }
};
</script>

<style lang="less" scoped></style>
