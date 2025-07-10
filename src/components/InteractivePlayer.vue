<template>
  <div class="interaction-area">
    <button
      class="trigger-button"
      @mousedown="startHold"
      @mouseup="cancelHold"
      @mouseleave="cancelHold"
      @touchstart="startHold"
      @touchend="cancelHold"
    >
      🎬 启动数字人
    </button>

    <!-- 视频区域 -->
    <video
      ref="videoRef"
      src="/avatar.mp4"
      poster="/avatar.png"
      class="avatar-video"
      preload="metadata"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 视频播放引用
const videoRef = ref(null)

// 音频预加载
const audio = new Audio('/audio/voice.mp3')

// 长按定时器
let holdTimer = null

function startHold() {
  // 用户开始按下时，设置定时器
  holdTimer = setTimeout(() => {
    playMedia()
  }, 2000) // 持续2秒后触发
}

function cancelHold() {
  // 用户松手时，清除定时器
  if (holdTimer) {
    clearTimeout(holdTimer)
    holdTimer = null
  }
}

function playMedia() {
  const video = videoRef.value
  if (video) {
    video.currentTime = 0
    audio.currentTime = 0
    video.play()
    audio.play()
  }
}
</script>

<style scoped>
.interaction-area {
  text-align: center;
  margin-top: 40px;
}

.trigger-button {
  padding: 12px 24px;
  background-color: #1e90ff;
  color: white;
  font-size: 18px;
  font-weight: bold;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  transition: background-color 0.3s ease;
}

.trigger-button:hover {
  background-color: #0d6efd;
}

.avatar-video {
  width: 360px;
  margin-top: 20px;
  border-radius: 12px;
  background: black;
}
</style>
