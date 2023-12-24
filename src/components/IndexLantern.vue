<template>
  <img id="lantern" ref="lantern" src="@/assets/lantern.png" />
</template>

<style scoped>
#lantern {
  transform-origin: center top;
  height: 180px;
  width: auto;
}
</style>

<script lang="ts" setup>
import { ref } from 'vue'
const lantern = ref<any>(null)

let data = {
  angle: 0,
  motion: 0,
  position: 'right',
  reach_toped: false
}

setInterval((data:any) => {
  if (data.angle < 0 && data.position == 'right' && data.reach_toped) {
    data.position = 'left'
    data.motion = -3
    data.reach_toped = false
  }
  else if (data.angle > 0 && data.position == "left" && data.reach_toped) {
    data.position = "right"
    data.motion = 3
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
  data.angle += data.motion * 0.2
  lantern.value.style.transform = `rotate(${data.angle}deg)`
}, 40, data);
</script>
