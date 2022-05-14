<template>
  <div class="header">
    <div class="header-inner">
      <div class="hidden-spacer"/>
      <div class="top-logo">
        <NuxtLink to="/"><AriLogo/></NuxtLink>
      </div>
      <nav
        class="nav"
        :style="{opacity: displayNav ? '1' : '0'}"
      >
        <NuxtLink to="/#projekte" class="nav-el">
          Projekte
        </NuxtLink>
        <NuxtLink to="/blog" class="nav-el">
          Blog
        </NuxtLink>
        <NuxtLink to="/downloads" class="nav-el">
          Downloads
        </NuxtLink>
        <NuxtLink to="/kontakt" class="nav-el">
          Kontakt
        </NuxtLink>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TopHeader',
  props: {
    displayNav: {
      type: Boolean,
      default: false
    },
  }
}
</script>

<style lang="scss">
  .header{
    display: flex;
    justify-content: center;
    width: 100%;
    position: fixed;
    padding-top: 8px;
    padding-bottom: 8px;
    z-index: 2;
  }
  .header-inner{
    display: grid;
    grid-auto-columns: minmax(0, 1fr);
    grid-auto-flow: column;
    align-items: center;
    max-width: 1504px;
    width: 100%;
    > * {
      flex-basis: 100%;
    }
  }
  .hidden-spacer {
    visibility: hidden;
  }
  .top-logo {
    display: flex;
    justify-content: center;
  }
  .nav{
    display: flex;
    gap: 32px;
    justify-content: right;
    transition: opacity 80ms ease;
    .nav-el {
      width: 96px;
      display: block;
      text-align: center;
    }
  }
</style>