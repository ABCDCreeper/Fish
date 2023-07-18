<template>
  <n-card title="现在喂食">
    <n-button @click="feednow">立即投喂！</n-button>
  </n-card>

  <n-card title="开关">
    <n-space>
      <n-tag> 灯光 </n-tag>
      <n-switch v-model:value="light_active" />
    </n-space>

    <n-space>
      <n-tag> 增氧 </n-tag>
      <n-switch v-model:value="oxygen_active" />
    </n-space>

    <n-space>
      <n-tag> 过滤 </n-tag>
      <n-switch v-model:value="filter_active" />
    </n-space>
  </n-card>

  <n-card title="定时投喂">
    <n-space>
    <n-tag> 启用 </n-tag>
    <n-switch v-model:value="feedtime_active" />
    </n-space>
    <n-time-picker v-model:value="feedtime1" format="h:mm a" :disabled="!feedtime_active" />
    <n-time-picker v-model:value="feedtime2" format="h:mm a" :disabled="!feedtime_active" />
    <n-time-picker v-model:value="feedtime3" format="h:mm a" :disabled="!feedtime_active" />
  </n-card>
</template>

<style scoped>
.n-card {
  max-width: 300px;
  margin-top: 5%;
  margin-left: 5%;
}
</style>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup () {
    const message = useMessage()
    return {
      light_active: ref(false),
      oxygen_active: ref(false),
      filter_active: ref(false),
      feedtime_active: ref(true),
      feedtime1: ref(null),
      feedtime2: ref(null),
      feedtime3: ref(null),
    }
  }
})
</script>