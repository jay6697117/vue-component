<template>
  <button :class="'i-button-size-' + size" :disabled="disabled" @click="clickHandle">
    <div class="icon-slot">
      <slot name="icon">
        <!-- 具名插槽默认内容 -->
        <span class="icon-default"></span>
      </slot>
      <slot>
        <!-- 匿名插槽默认内容 -->
        default按钮
      </slot>
    </div>
  </button>
</template>

<script>
// 判断参数是否是其中之一
function oneOf(value, validList) {
  for (let i = 0; i < validList.length; i++) {
    if (value === validList[i]) {
      return true;
    }
  }
  return false;
}

export default {
  inheritAttrs: false,
  data() {
    return {
      title: 'i-button组件'
    };
  },
  props: {
    size: {
      default: 'default',
      validator(value) {
        return oneOf(value, ['small', 'large', 'default']);
      }
    },
    disabled: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    clickHandle() {
      this.$emit('click', this.size);
    }
  }
};
</script>
<style lang="less" scoped>
.i-button-size-default {
  margin: 5px;
  padding: 10px 30px;
  background-color: #cccccc;
}
.i-button-size-small {
  margin: 5px;
  padding: 5px 15px;
  background: red;
}
.i-button-size-large {
  margin: 5px;
  padding: 20px 60px;
  background: blue;
}
.icon-slot {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.icon-default {
  margin-right: 5px;
  display: inline-block;
  width: 19px;
  height: 19px;
  background: yellow;
  border-radius: 50%;
}
</style>
