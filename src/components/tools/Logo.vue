<template>
  <div :class="device!=='mobile'?'logo logo-device':'logo'">
    <router-link :to="{name:'dashboard'}">
      <!-- <img src="~@/assets/logo.svg" alt="logo"> -->
      <span v-if="showTitle">{{ title }}</span>
    </router-link>
  </div>
</template>

<script>
import { mixin, mixinDevice } from '@/utils/mixin.js'
  export default {
    name: 'Logo',
    mixins: [mixin, mixinDevice],
    props: {
      title: {
        type: String,
        default: 'LOGO',
        required: false
      },
      showTitle: {
        type: Boolean,
        default: true,
        required: false
      }
    }
  }
</script>

<style lang="less" scoped>
  .logo{
    font-size:16px;
    font-weight:bold;
    &.logo-device {
      display: inline-block;
      line-height: 64px;
    }
    & a{
      color:#333;
    } 
  }
</style>