<template lang="pug">
#app
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
      imgUrls: ['static/img/1.jpg', 'static/img/2.jpg', 'static/img/3.jpg', 'static/img/4.jpg', 'static/img/5.jpg', 'static/img/6.jpg', 'static/img/7.jpg', 'static/img/8.jpg', 'static/img/9.jpg', 'static/img/10.jpg','static/img/11.jpg', 'static/img/12.jpg'],

      // imgUrls: ['static/img/1.jpg', 'static/img/2.jpg', 'static/img/3.jpg', 'static/img/4.jpg', 'static/img/5.jpg', 'static/img/6.jpg', 'static/img/7.jpg', 'static/img/8.jpg', 'static/img/9.jpg', 'static/img/10.jpg', 'static/img/11.jpg', 'static/img/12.jpg', 'static/img/13.jpg', 'static/img/14.jpg', 'static/img/15.jpg', 'static/img/16.jpg', 'static/img/17.jpg', 'static/img/18.jpg', 'static/img/19.jpg', 'static/img/20.jpg'],
      preLoaded: false // 预加载是否完成
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
    img {
      width: 25%;
    }
  }
}
</style>
