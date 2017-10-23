<template lang="pug">
#app(:class="{'is-mobile':isMobile}")
  preload-image(:imgUrlArr="imgUrls", @imgAllLoaded="fn")

  .imgs-container(v-if="preLoaded")
    img(v-for="(v,i) in imgUrls",:src="v",:alt="`第${i+1}张图片`",:title="`第${i+1}张图片`")
</template>

<script>
import preloadImage from 'components/vue-preload-image.vue'


export default {
  name: 'app',
  components: {
    preloadImage
  },
  data() {
    return {
      imgUrls: ['static/img/1.jpg', 'static/img/2.jpg', 'static/img/3.jpg', 'static/img/4.jpg', 'static/img/5.jpg', 'static/img/6.jpg', 'static/img/7.jpg', 'static/img/8.jpg', 'static/img/9.jpg', 'static/img/10.jpg', 'static/img/11.jpg', 'static/img/12.jpg'],

      preLoaded: false, // 预加载是否完成
      isMobile: !!navigator.userAgent.match(/(iPhone|iPod|Android|ios)/i)
    }
  },
  methods: {
    fn() {
      this.preLoaded = true
    },
  }
}
</script>

<style lang="scss">
html,
body {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
}

#app {
  .imgs-container {
  background: #000;

    img {
      width: 25%;
    }
  }
  &.is-mobile {
    .imgs-container {
      img {
        width: 50%;
      }
    }
  }
}
</style>
