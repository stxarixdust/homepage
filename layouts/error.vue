<template>
  <div id="errorContainer" class="container">
    <div id="error">
      <h1>Error {{error.statusCode}}</h1>
      <p>
        <span v-if="error.statusCode === 403">Auf diese Seite kann nicht zugegriffen werden</span>
        <span v-else-if="error.statusCode === 404">Diese Seite konnte nicht gefunden werden</span>
        <span v-else-if="error.statusCode === 500">Ein interner Error hat stattgefunden</span>
        <span v-else-if="error.statusCode === 505">Ein interner Error hat stattgefunden</span>
        <span v-else>Ein Error hat stattgefunden</span>. Falls dieser Fehler unerwartet ist, schicken Sie mir eine E-Mail
      </p>
      <div class="buttonsContainer">
        <NuxtLink to="/"><Button primary>Zur Homepage</Button></NuxtLink>
        <a href="mailto://sylveon_ari@hotmail.com"><Button external>E-Mail schicken</Button></a>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['error']
  }
</script>

<style lang="scss">
  #errorContainer{
    display: flex;
    width: 1504px;
    margin: auto;
    height: 100vh;
  }
  #error{
    width: 480px;
    margin-top: 96px;
    >* {
      margin-bottom: 32px;
      margin-top: 0;
    }
  }
</style>