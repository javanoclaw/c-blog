<template>
  <div class="main_wrap" id="particles-js">
    <Header/>
    <div class="flex_wrap">
      <NavMenu/>
      <div class="content_wrap">
        <nuxt/>
      </div>
    </div>
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import NavMenu from '../components/NavMenu.vue'
import particlesConfig from '@/assets/particles.json'

export default {
  components: {
    Header,
    NavMenu
  },
  mounted() {
    this.$nextTick(function () {
      window.particlesJS('particles-js', particlesConfig)
    })
  }
}
</script>

<style scoped lang="scss">
#particles-js {
    position: relative;
}
.main_wrap {
  min-width: $min-width;
  color: #282828;
  display: flex;
  flex-direction: column;
  .flex_wrap {
    display: flex;
    height: calc(100% - 67px);
    overflow: hidden;
    .content_wrap {
      flex: 1;
      height: 100%;
      overflow-y: scroll;
    }
  }
}
</style>
