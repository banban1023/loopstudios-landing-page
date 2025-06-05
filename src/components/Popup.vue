<template>
  <transition name="fade">
    <div class="popup_content" v-if="visible">
      <p>logo</p>
      <slot></slot>
      <button class="popup_close" @click="handleClose">×</button>
    </div>
  </transition>
</template>

<script>
export default {
  name: 'PopupVue',
  props: {
    value: {
      type: Boolean,
      required: true
    }
  },
  computed: {
    visible: {
      get () {
        return this.value
      },
      set (val) {
        this.$emit('input', val)
      }
    }
  },
  methods: {
    handleClose () {
      this.visible = false
    }
  }
}
</script>

<style lang="less" scoped>
.popup_content {
  background-color: #000;
  padding: 40px 25px 0;
  left: 0;
  top: 0;
  position: fixed;
  width: 100%;
  height: 100vh;
  line-height: 50px;
  font-size: 18px;
  z-index: 100;
  color: #fff;
  font-size: 25px;
  font-weight: 300;
  p {
    width: 145px;
    height: 25px;
    font-size: 0;
    background: url('../assets/images/logo.svg') no-repeat center center;
    background-size: contain;
    margin-bottom: 140px;
  }
}

.popup_close {
  position: absolute;
  top: 44px;
  left: 331px;
  width: 20px;
  height: 20px;
  background: none;
  border: none;
  font-size: 0;
  cursor: pointer;
  background: url('../assets/images/icon-close.svg') no-repeat;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
