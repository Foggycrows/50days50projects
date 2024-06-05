<script setup>
import { ref, computed } from 'vue'

let activeNum = ref(1)
let prevDisabled = computed(() => {
  return activeNum.value === 1
})
let nextDisabled = computed(() => {
  return activeNum.value === 4
})
const prevClick = () => {
  activeNum.value--
}
const nextClick = () => {
  activeNum.value++
}
</script>

<template>
  <div class="container">
    <div class="progress-container">
      <div class="progress active">1</div>
      <div class="line" :class="[activeNum >= 2 ? 'active' : '']">
        <div class="line-change" :class="[activeNum >= 2 ? 'active' : '']"></div> 
      </div>
      <div class="progress" :class="[activeNum >= 2 ? 'active' : '']">2</div>
      <div class="line" :class="[activeNum >= 3 ? 'active' : '']" >
        <div class="line-change" :class="[activeNum >= 3 ? 'active' : '']"></div>
      </div>
      <div class="progress" :class="[activeNum >= 3 ? 'active' : '']">3</div>
      <div class="line" :class="[activeNum >= 4 ? 'active' : '']" >
        <div class="line-change" :class="[activeNum >= 4 ? 'active' : '']"></div>
      </div>
      <div class="progress" :class="[activeNum >= 4 ? 'active' : '']">4</div>
    </div>
    <div class="button-container">
      <button class="btn prev" :disabled="prevDisabled" @click="prevClick">Prev</button>
      <button class="btn next" :disabled="nextDisabled" @click="nextClick">Next</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  position: relative;
  width: 420px;
  height: 80px;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
}
.progress-container {
  position: relative;
  display: flex;
}
.progress {
  height: 30px;
  width: 30px;
  text-align: center;
  line-height: 30px;
  border: 3px, solid white;
  border-radius: 50%;
  transition: all 1s;
}
.progress.active {
  border: 3px, solid #3498db;
}
.line {
  width: 100px;
  height: 4px;
  background-color: #fff;
  margin-top: 14px;
}
.line-change {
  width: 0;
  height: 4px;
  background-color: #3498db;
  transition: all 1s;
}
.line-change.active {
  width: 100%;
}
.button-container {
  display: flex;
  width: 100%;
  height: 100%;
  justify-content: center;
}
.btn {
  margin-top: 30px;
  width: 100px;
}
.btn.prev {
  margin-right: 15px;
}
.btn.next {
  margin-left: 15px;
}
</style>
