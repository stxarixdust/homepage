<template>
  <div class="section layout-right">
    <div class="inner-constraint">
      <div class="inner-content">
        <h1>Mein Name ist Ari</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec purus arcu, finibus et luctus id, faucibus vel nisl. Suspendisse venenatis metus vel mauris lacinia, eget sodales nunc aliquam. Morbi suscipit nisi vel nibh fringilla, non commodo orci consectetur. Curabitur rutrum diam cursus hendrerit dignissim. Suspendisse gravida libero vel aliquam ultricies. Praesent id elementum magna, eget semper augue. Phasellus sed erat in mi congue porta.
        </p>
        <p>
          Quisque et sollicitudin nibh. Aliquam varius tortor quis gravida euismod. Ut arcu neque, interdum condimentum justo a, aliquet pretium purus. Nam vel urna id lectus congue placerat. Donec luctus consectetur lorem ac interdum. Nulla faucibus vitae elit id volutpat. Donec tempus, enim eget finibus tempor, quam tortor iaculis justo, et volutpat sem nunc id ante. Ut pharetra urna mauris, in ultricies nisl ornare in. Nulla pharetra nisi metus, ut iaculis ex consectetur sit amet.
        </p>
        <div id="intro-buttons">
          <Button primary width="96px">Projekte</Button>
          <Button width="96px">Blog</Button>
          <Button width="96px">Downloads</Button>
          <Button width="96px">Kontakt</Button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style lang="scss">
  .section {
    min-height: 100vh;
    .inner-constraint{
      max-width: 1504px;
      margin: auto;
    }
    .inner-content{
      width: 480px;
      position: relative;
      top: 96px;
      >* {
        margin-bottom: 32px;
      }
    }
    &.layout-right .inner-content {
      margin-left: auto; 
      margin-right: 0;
    }
  }
</style>