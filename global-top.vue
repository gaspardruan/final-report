<script setup lang="ts">
import { ref } from 'vue';
import VueCountdown from '@chenfengyuan/vue-countdown';
const ready = ref(false);

const start = () => {
  ready.value = true;
};

</script>

<template>
<div class="absolute top-0 left-0">
  <button type="button" v-if="!ready" @click="start" class="text-red-700 px-3 py-2 text-xs font-medium text-center ">Start Timer</button>
  <vue-countdown class="px-1 py-1 text-xs font-medium text-red-700" v-if="ready" :time="1 * 1 * 10 * 60 * 1000" v-slot="{ minutes, seconds }">
    {{ minutes }}:{{ seconds }}
  </vue-countdown>
</div>

</template>