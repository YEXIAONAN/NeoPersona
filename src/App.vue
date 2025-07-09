<script setup>
import HelloWorld from './components/HelloWorld.vue'
import BgURL from './assets/bg.jpg'
</script>

<template>



<h1>NeoPersona - 本地数字人</h1>
<h3>Your Private, Intelligent Digital Human - by yexiaonan</h3>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.image-wrapper {
  width: 100%;
  max-width: 600px; /* 最大宽度限制 */
  margin: 0 auto; /* 居中显示 */
}

.responsive-img {
  width: 100%;
  height: auto; /* 保持原图比例 */
  display: block;
  border-radius: 8px; /* 可选：圆角 */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1); /* 可选：阴影 */
}
</style>
