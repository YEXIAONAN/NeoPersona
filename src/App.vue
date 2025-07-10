<script setup>
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
import BgURL from './assets/bg.jpg' // 背景图（如需展示）
import AvatarVideo from './components/AvatarVideo.vue'
import InteractivePlayer from './components/InteractivePlayer.vue'
// 音频路径（放 public/audio/voice.mp3）
const audioUrl = '/audio/voice.mp3'
const audioRef = ref(null)

const playAudio = () => {
  if (audioRef.value) {
    audioRef.value.play()
  }
}
</script>

<template>
<AvatarVideo />

  <h1>NeoPersona - 本地数字人</h1>
  <h3>Your Private, Intelligent Digital Human - by yexiaonan</h3>

<button class="ask-button">🩺 询问健康顾问</button>
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
  max-width: 600px;
  margin: 0 auto;
  text-align: center;
}

.responsive-img {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  transition: transform 0.2s;
}
.responsive-img:hover {
  transform: scale(1.02);
}

.ask-button {
  padding: 12px 24px;
  background: linear-gradient(135deg, #3f8efc, #56ccf2);
  color: white;
  font-size: 16px;
  font-weight: bold;
  border: none;
  border-radius: 999px;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.ask-button:hover {
  background: linear-gradient(135deg, #347be6, #3fa9f5);
  transform: scale(1.03);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.15);
}
</style>
