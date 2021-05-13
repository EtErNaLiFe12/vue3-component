<!--MyBtn-1
<template>
  <div 
    :class="{ large }"
    :style="{ backgroundColor: color }"
    class="btn">
    <slot></slot>
  </div>
</template>

<script>
export default {
    props: {
      color: {
        type: String,
        default: 'gray'
    },
    large: {
      type: Boolean,
      default: false
    }
    // text: {
    //   type: String,
    //   default: ''
    // }
  }
}
</script>
<style scoped lang="scss">
  .btn {
      display: inline-block;
      margin: 4px;
      padding: 6px 12px;
      border-radius: 4px;
      background-color: gray;
      color: white;
      cursor: pointer;
      &.large {
      font-size: 20px;
      padding: 10px 20px;
    }
  }
  
</style>-->

<!--MyBtn-2-->
<template>
  <div class="btn">
    <slot></slot>
  </div>
  <h1 v-bind="$attrs"></h1>
  <div v-bind="$attrs"></div>
</template>

<script>
export default {
  inheritAttrs: false,
  created() {
    console.log(this.$attrs)
  }
}
</script>

<style scoped>
  .btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }
</style>
