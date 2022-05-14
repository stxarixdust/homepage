<template>
  <div>
    <TopHeader
      :displayNav="!showIntroBtns"
    />
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
          <div
            id="intro-buttons"
            :style="{opacity: showIntroBtns ? '1' : '0'}"
          >
            <a href="#projekte"><Button primary width="96px">Projekte</Button></a>
            <NuxtLink to="blog" class="nav-el">
              <Button width="96px">Blog</Button>
            </NuxtLink>
            <NuxtLink to="downloads" class="nav-el">
              <Button width="96px">Downloads</Button>
            </NuxtLink>
            <NuxtLink to="kontakt" class="nav-el">
              <Button width="96px">Kontakt</Button>
            </NuxtLink>
          </div>
        </div>
        <StartBg
          id="startBg"
        />
        <img
          v-if="scrollPos < 1"
          id="ariStartImg"
          src="ariFloat.png"
          :style="{top: (100 - scrollPos * 33) + 'vh'}"
        >
      </div>
      <div id="bottomFade"/>
    </div>
    <div id="projekte" class="section-title">
      <h1>Projekte</h1>
      <p>
        Hier sind einige meiner vergangenen persönlichen, aufträglichen, oder schulischen Projekte.
      </p>
    </div>
    <div id="projekte" class="section layout-right">
      <div id="desc">
        <div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  transition: 'index',
  data: () => ({
    scrollPos: 0,
    showIntroBtns: true
  }),
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll () {
      this.scrollPos = window.scrollY / window.innerHeight;
      this.showIntroBtns = document.getElementById("intro-buttons").offsetTop - window.scrollY + window.screenY + document.getElementById("intro-buttons").clientHeight > 0;
    }
  },
}
</script>

<style lang="scss">
  .index-enter-active, .index-leave-active {
    transition: all .5s;
  }
  .index-enter, .index-leave-active {
    opacity: 0;
    transform: scale(1.1);
    #ariStartImg {
      transform: translate(-64px,-100%);
    }
    #bottomFade{
      height: 512px;
    }
  }

  #ariStartImg {
    transition: transform .5s;
    position: absolute;
    height: calc(100vh - 96px);
    left: 0;
    top: 100vh;
    transform: translate(0px,-100%);
    mask-image: linear-gradient(to bottom, rgba(0,0,0,1) 75%, rgba(0,0,0,0));
  }
  #startBg {
    position: absolute;
    left: 0;
    top: 0;
    height: 100vh;
    width: auto;
  }
  #bottomFade{
    position: absolute;
    height: 256px;
    width: 100vw;
    left: 0;
    top: 100vh;
    transform: translate(0px,-100%);
    background: linear-gradient(to bottom, #DFE6E900, #DFE6E9);
  }
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
      z-index: 1;
      >* {
        margin-bottom: 32px;
      }
    }
    &.layout-right .inner-content {
      margin-left: auto; 
      margin-right: 0;
    }
  }
  #intro-buttons {
    position: sticky;
    display: flex;
    gap: 32px;
    transition: opacity 80ms ease;
  }
</style>