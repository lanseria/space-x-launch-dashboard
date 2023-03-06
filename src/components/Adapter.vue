<script setup lang="ts">
import { onMounted, reactive } from 'vue'

const props = defineProps({
  width: {
    type: String,
    default: '1920',
  },
  height: {
    type: String,
    default: '1080',
  },
})
const style = reactive({
  width: `${props.width}px`,
  height: `${props.height}px`,
  transform: 'scale(1) translate(-50%, -50%)',
})

const Debounce = (fn: any, t: any) => {
  const delay = t || 500
  let timer: any
  return () => {
    // eslint-disable-next-line @typescript-eslint/ban-ts-comment
    // @ts-expect-error

    const args = arguments
    if (timer)
      clearTimeout(timer)

    timer = setTimeout(() => {
      timer = null
      fn.apply(this, args)
    }, delay)
  }
}
// 获取放大缩小比例
const getScale = () => {
  const w = window.innerWidth / +props.width
  const h = window.innerHeight / +props.height
  return w < h ? w : h
}
// 设置比例
const setScale = () => {
  style.transform = `scale(${getScale()}) translate(-50%, -50%)`
  console.warn('任你千变万化,我都不会影响性能')
}
onMounted(() => {
  setScale()
  window.onresize = Debounce(setScale, 1000)
})
</script>

<template>
  <div class="screen-adapter" :style="style">
    <slot />
  </div>
</template>

<style lang="css" scoped>
.screen-adapter {
  /* background-color: #060D53; */
  transform-origin: 0 0;
  position: absolute;
  left: 50%;
  top: 50%;
  transition: 0.3s;
  background: url('https://img.js.design/assets/img/6404915df4ca82978f454317.png#00a2a7ad9c4bd9f4ecd56427626d54c0');
  background-size: 100% 100%;
}
</style>
