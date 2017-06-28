## 为什么使用vue-preload-image

当网页中存在大量图片，且网速缓慢时，会带来极差的用户体验。
我们可以利用**加载页面**来**预加载图片资源**，获得流畅的用户体验。
## [DEMO](https://lfyfly.github.io/vue-preload-image/)
## [github](https://github.com/lfyfly/vue-preload-image)
## 适用于vue2.x
## 安装
```
npm install vue-preload-image -save-dev
```
## 局部引用
```js
import preloadImage from 'vue-preload-image'
```
```js

export default {
  name: 'app',
  components: {
    preloadImage
  }
}

```
## 全局引用(在main.js中)
```js
  import preloadImage from 'vue-preload-image'
  Vue.component('preload-image', preloadImage)
```

## 组件参数
```js
  props: {
    // 需要预加载的图片url组成的数组
    imgUrlArr: {
      type: Array,
      required: true,
    },
    // 控制显示
    animationShow: { // 控制加载动画的显示
      type: Boolean,
      default: true,
    },
    tipStrShow: { // 控制文字提示信息的显示
      type: Boolean,
      default: true,
    },
    progressShow: { // 控制图片加载进程文字的显示
      type: Boolean,
      default: true
    },
    progressType: { // 图片加载进程文字的类型
      type: String,
      default: 'percent' // 'percent' 百分比类型 | 'count' 加载图片数量类型
    },
    order: { // 图片有序加载的
      type: Boolean,
      default: true
    },
    tipStr: { // 图片预加载中的提示语内容
      type: String,
      default: '图片预加载中...'
    }
  }
```
## 组件事件
### imgAllLoader
 图片全部加载完成后执行
```html
<preload-image :imgUrlArr="imgUrls" @imgAllLoaded="fn"></preload-image>
```
## 通过slot使用自定义加载动画
```html
<preload-image :imgUrlArr="imgUrls" @imgAllLoaded="fn" :animationShow="false">
  <img src="your-loading.gif" />
</preload-image>
```
