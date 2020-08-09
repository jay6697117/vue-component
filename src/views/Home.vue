<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div>

      <i-button ref="iButton1" id="largeId" class="largeClass" size="large" @btn-click="btnClickHandle">
        <span slot="icon" class="icon-logo"></span>
        <span>large按钮</span>
      </i-button>

      <hr />

      <i-button id="defaultd" class="defaultClass" size="default" @btn-click="btnClickHandle"></i-button>

      <hr />

      <i-button id="smallId" class="smallClass" size="small" @btn-click="btnClickHandle">
        <span slot="icon" class="icon-wps"></span>
        <span>small按钮</span>
      </i-button>

      <hr />

      <i-button
        ref="iButton4"
        id="disabledId"
        class="disabledClass"
        :disabled="true"
        @btn-click="btnClickHandle"
      ></i-button>

      <div>App nameObj: {{nameObj}}</div>

    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import IButton from '@/components/IButton.vue';
export default {
  name: 'Home',
  data() {
    return {
      title: 'Home页面'
    };
  },
  inject:['nameObj'],
  components: {
    'i-button': IButton
  },
  methods: {
    btnClickHandle(sizeName) {
      console.log('Home btnClickHandle sizeName :>> ', sizeName);
    }
  },
  mounted() {
    console.log('this.$refs.iButton1 :>> ', this.$refs.iButton1);
    console.log('this.$refs.iButton4 :>> ', this.$refs.iButton4);
    console.log('this.$refs.iButton1.title :>> ', this.$refs.iButton1.title);
    console.log('this.$refs.iButton4.title :>> ', this.$refs.iButton4.title);
    this.$refs.iButton1.clickHandle();
    this.$refs.iButton4.clickHandle();
    console.log('$parent :>> ', this.$parent);
    console.log('$children :>> ', this.$children);
  }
};
</script>
<style lang="less" scoped>
.home {
  background-color: #cccccc;
}
.icon-logo {
  margin-right: 5px;
  display: inline-block;
  width: 19px;
  height: 19px;
  background-image: url('../assets/logo.png');
  background-repeat: no-repeat;
  background-size: 100% 100%;
}
.icon-wps {
  margin-right: 5px;
  display: inline-block;
  width: 19px;
  height: 19px;
  background-image: url('../assets/wps.png');
  background-repeat: no-repeat;
  background-size: 100% 100%;
}
</style>
