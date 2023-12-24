<template>
    <img src="@/assets/flower.png" id="flower" ref="flower" />
</template>

<style scoped>
#flower {
  transform-origin: center center;
  height: 128px;
  width: auto;
  position: absolute;
}
</style>

<script lang="ts" setup>
import { ref } from 'vue'
const flower = ref<any>(null)

let data = {
  swing: 0,
  angle: 0,
  motion: 0,
  position: 'right',
  reach_toped: false,
  y: (Math.random() - 1) * (screen.availHeight),
  x: Math.random() * screen.availWidth
}

setInterval((data:any) => {
  data.angle += 2;
  if (data.swing < 0 && data.position == 'right' && data.reach_toped) {
    data.position = 'left'
    data.motion = -4
    data.reach_toped = false
  }
  else if (data.swing > 0 && data.position == "left" && data.reach_toped) {
    data.position = "right"
    data.motion = 4
    data.reach_toped = true
  }
  if (data.position == 'right') {
    data.motion -= 0.2
    if (data.motion < 0) {
        data.reach_toped = true
    }
  } else {
    data.motion += 0.2
    if (data.motion > 0) {
        data.reach_toped = true
    }
  }
  data.swing += data.motion * 0.2
  flower.value.style.transform = `rotate(${data.angle}deg)`
  
  data.y += 2;
  if (data.y > screen.availHeight) {
    data.y = (Math.random() - 1) * (screen.availHeight)
    data.x = Math.random() * screen.availWidth

}

  flower.value.style.top = `${data.y}px`
  flower.value.style.left = `${data.x}px`
}, 20, data);
</script>
