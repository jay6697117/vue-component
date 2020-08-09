<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ComptA />
    <ComptB />
    <FatherComp />
  </div>
</template>
<script>
import ComptA from '../components/ComptA';
import ComptB from '../components/ComptB';
import FatherComp from '../components/FatherComp';
export default {
  name: 'About',
  components: {
    ComptA,
    ComptB,
    FatherComp
  },
  data() {
    return {
      title: 'About页面'
    };
  }
};
</script>
<style lang="less" scoped></style>
