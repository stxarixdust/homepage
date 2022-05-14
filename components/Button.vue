<template>
  <div
    class="button"
    :class="{primary: primary, fixedWidth: width != ''}"
    :style="width != '' ? ('width: '+width) : ''"
  >
    <span><slot></slot></span>
    <ExternalLink v-if="external"/>
  </div>
</template>

<script>
export default {
  props:{
    primary: Boolean,
    external: Boolean,
    width: {
      default: "",
      type: String
    }
  }
}
</script>