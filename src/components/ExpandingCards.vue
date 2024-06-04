<script setup>
import { ref } from 'vue'
const list = ref([{
  id: 1,
  title: '标题',
  src: '../asset/ExpandingCards/2.jpg',
},
{
  id: 2,
  title: '标题',
  src: '../asset/ExpandingCards/2.jpg',
},
{
  id: 3,
  title: '标题',
  src: '../asset/ExpandingCards/2.jpg',
},
{
  id: 4,
  title: '标题',
  src: '../asset/ExpandingCards/2.jpg',
},
{
  id: 5,
  title: '标题',
  src: '../asset/ExpandingCards/2.jpg',
}])
let activeId = ref(1);
const setActive = (id) => {
  activeId.value = id
}
</script>

<template>
  <div class="container">
    <div 
      class="panel" 
      :class="[activeId === item.id ? 'active' : '',
          `imgId${item.id}`
        ]"
      @click="setActive(item.id)" 
      v-for="item in list" 
      :key="item.id"
    >
      <!-- <img :src="item.src" alt=""> -->
      <h3>item.title</h3>
    </div>
  </div>
</template>

<style scoped>
.container {
  width: 80vw;
  display: flex;
  /* background-color: black; */
  justify-content: space-between;
  position: absolute;
  left: 50vw;
  top: 50vh;
  transform: translate(-50%, -50%);
  
}
.panel {
  position: relative;
  height: 80vh;
  /* background-color: red; */
  border-radius: 30px;
  flex: 0.5;
  cursor: pointer;
  transition: all 1s;
  margin: 10px;
  /* background-image: url(../asset/1.jpg); */
}
.panel.imgId1 {
  background-image: url(../asset/2.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.panel.imgId2 {
  background-image: url(../asset/1.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.panel.imgId3 {
  background-image: url(../asset/2.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.panel.imgId4 {
  background-image: url(../asset/1.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.panel.imgId5 {
  background-image: url(../asset/2.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.panel h3{
  font-size: 40px;
  position: absolute;
  top: 85%;
  left: 10%;
  opacity: 0;
}

.panel.active {
  flex: 5;
}

.panel.active h3 {
  opacity: 1;
  transition: opacity 0.3s ease-in 0.4s;
}
</style>
