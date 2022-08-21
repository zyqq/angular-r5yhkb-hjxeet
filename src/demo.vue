<!-- 文档说明visible、v-model、v-model:visible 都可控制显示，但是 visible 显示后会无法关闭 -->
<template>
  <div class="popup-base">
    <t-button theme="primary" @click="center = true">中部弹出</t-button>
    <t-popup :visible="center" placement="center">
      <div style="width: 200px; height: 200px; background: #fff"></div>
    </t-popup>
    <t-button theme="primary" @click="right = true">右侧弹出</t-button>
    <t-popup v-model="right" placement="right">
      <div style="width: 200px; height: 200px; background: #fff"></div>
    </t-popup>
    <t-button theme="primary" @click="left = true">左侧弹出</t-button>
    <t-popup v-model:visible="left" placement="left">
      <div style="width: 200px; height: 200px; background: #fff"></div>
    </t-popup>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const center = ref(false);
    const left = ref(false);
    const right = ref(false);

    return {
      center,
      left,
      right,
    };
  },
});
</script>
