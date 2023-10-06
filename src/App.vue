<script setup lang="ts">
    import { RouterView } from 'vue-router';
    import { ref, computed } from 'vue';
    import { ElButton, ElInput, ElDatePicker } from 'element-plus';
  
 const selectedColor = ref('#00FF00'); 
 const selectedColorbor = ref(getRandomColor());

function getRandomColor() {
  const letters = '0123456789ABCDEF';
  let color = '#';
  for (let i = 0; i < 6; i++) {
    color += letters[Math.floor(Math.random() * 16)];
  }
  return color;
}
  
  function updateBorderColor() {
  selectedColorbor.value = getRandomColor();
}
</script>

<template>
    <div class="color-box" :style="{ backgroundColor: selectedColor,border:'6px solid'+selectedColorbor}">
      <H1>顏色選擇器</H1>
      <div>
  <input type="color" v-model="selectedColor" @input="updateBorderColor" />
      </div>
      <p>選擇的顏色: {{ selectedColor }}</p>
    </div>
</template>
<style>
.color-box {
  width: 100%;
  height: 1000px;
  display: block;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-size: 18px;
}
</style>
