<template>
  <div class="modal-wrapper" :class="[isShow?'show':'']">
    <div class="modal-header">
      <div class="btn-close" @tap="close">
        <span class="iconfont icon-close"></span>
      </div>
      <slot name="title"></slot>
      <div></div>
    </div>
    <div class="modal-content">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isShow: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    close () {
      this.$emit('closeModal')
    }
  }
}
</script>

<style scoped>
  @import url("../../static/style/icon.css");
  .modal-wrapper{
    position:fixed;
    top:0;
    bottom:0;
    left:0;
    right:0;
    background:#fff;
    max-height:0;
    transform:rotate3d(1,0,0,-90deg);
    transition:all .3s ease-in-out;
    transform-origin:50% 0%;
  }
  .modal-wrapper.show{
    max-height:100%;
    transform:rotate3d(0,0,0,0deg);
  }
  .modal-wrapper .modal-header{
    height:100rpx;
    padding:0 40rpx;
    border-bottom:1px solid #f5f5f5;
    align-items:center;
    display:flex;
    justify-content:space-between;
  }
  .modal-wrapper .modal-content{
    position:absolute;
    top:100rpx;
    left:0;
    right:0;
    bottom:0;
    overflow:auto;
    padding:40rpx;
  }
</style>
