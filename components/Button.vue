<template>
  <div
    class="button"
    :class="{primary: primary, fixedWidth: width != 0}"
    :style="width != 0 ? ('width: '+width) : ''"
  >
    <slot></slot>
  </div>
</template>

<script>
export default {
  props:{
    primary: Boolean,
    width: {
      default: 0,
      type: Number
    }
  }
}
</script>