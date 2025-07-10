<template>
  <div class="video-container">
    <video
      ref="videoRef"
      :src="videoSrc"
      :poster="posterSrc"
      @click="handlePlay"
      class="avatar-video"
      preload="metadata"
    />
    <div class="play-button" v-if="!isPlaying" @click.stop="handlePlay">▶️</div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const videoSrc = '/avatar.mp4'     // SadTalker输出视频
const posterSrc = '/avatar.png'    // 封面图
const audioSrc = '/audio/voice.mp3'// TTS音频路径

const videoRef = ref(null)
const audioRef = ref(new Audio(audioSrc))  // 创建音频实例
const isPlaying = ref(false)

function handlePlay() {
  const video = videoRef.value
  const audio = audioRef.value

  if (!video || !audio) return

  // 若已播放，点击暂停
  if (!video.paused) {
    video.pause()
    audio.pause()
    isPlaying.value = false
  } else {
    // 播放视频和音频
    video.currentTime = 0
    audio.currentTime = 0
    video.play()
    audio.play()
    isPlaying.value = true
  }

  // 当视频播放完后自动重置
  video.onended = () => {
    isPlaying.value = false
    audio.pause()
  }
}
</script>

<style scoped>
.video-container {
  position: relative;
  width: 360px;
  margin: 0 auto;
  cursor: pointer;
}
.avatar-video {
  width: 100%;
  border-radius: 12px;
  background-color: #000;
}
.play-button {
  position: absolute;
  top: 45%;
  left: 45%;
  font-size: 32px;
  background: rgba(0, 0, 0, 0.4);
  color: white;
  border-radius: 50%;
  padding: 8px 12px;
  user-select: none;
}
</style>
