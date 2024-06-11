<script setup>
import { ref } from 'vue';
let isShow = ref(1)
function open() {
  isShow.value = 1
}
function close() {
  isShow.value = 0
}
</script>

<template>
  <div class="background">
    <div class="container" :class="[isShow === 1 ? 'show-nav' : '']">
      <div class="circle-container">
        <div class="circle" :class="[isShow === 1 ? 'show-nav' : '']">
          <button id="open" @click="open"><i class="iconfont icon-3column"></i></button>
          <button id="close" @click="close"><i class="iconfont icon-close"></i></button>
        </div>
      </div>
      <div class="content">
        <h1>Amazing Article</h1>
        <small>Florin Pop</small>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium quia in ratione dolores cupiditate, maxime aliquid impedit dolorem nam dolor omnis atque fuga labore modi veritatis porro laborum minus, illo, maiores recusandae cumque ipsa quos. Tenetur, consequuntur mollitia labore pariatur sunt quia harum aut. Eum maxime dolorem provident natus veritatis molestiae cumque quod voluptates ab non, tempore cupiditate? Voluptatem, molestias culpa. Corrupti, laudantium iure aliquam rerum sint nam quas dolor dignissimos in error placeat quae temporibus minus optio eum soluta cupiditate! Cupiditate saepe voluptates laudantium. Ducimus consequuntur perferendis consequatur nobis exercitationem molestias fugiat commodi omnis. Asperiores quia tenetur nemo ipsa.</p>
        <h3>My Dog</h3>
        <img src="../asset/ExpandingCards/1.jpg" alt="">
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Sit libero deleniti rerum quo, incidunt vel consequatur culpa ullam. Magnam facere earum unde harum. Ea culpa veritatis magnam at aliquid. Perferendis totam placeat molestias illo laudantium? Minus id minima doloribus dolorum fugit deserunt qui vero voluptas, ut quia cum amet temporibus veniam ad ea ab perspiciatis, enim accusamus asperiores explicabo provident. Voluptates sint, neque fuga cum illum, tempore autem maxime similique laborum odio, magnam esse. Aperiam?</p>
      </div>
    </div>
    <nav>
      <ul :class="[isShow === 1 ? 'show-nav' : '']">
        <li class="first"><i class="iconfont icon-home"> Home</i></li>
        <li class="second"><i class="iconfont icon-user"> User</i></li>
        <li class="third"><i class="iconfont icon-email"> Email</i></li>
      </ul>
    </nav>
  </div>
</template>

<style type="text/css">
    .icon {
       width: 1em; height: 1em;
       vertical-align: -0.15em;
       fill: currentColor;
       overflow: hidden;
    }
</style>

<style scoped>
.background {
  background-color: #313131;
  width: 100%;
  height: 100%;
}
.container {
  position: absolute;
  background-color: #fafafa;
  width: 100%;
  height: 100%;
  top: 0px;
  /* height: 100vh; */
  /* padding: 50px; */
  transform-origin: top left;
  transition: all 0.5s;
}
.container.show-nav {
  transform: rotate(-20deg);
}
.circle-container {
  position: fixed;
  left: -100px;
  top: -100px;
}
.circle {
  background-color: #ff7979;
  height: 200px;
  width: 200px;
  border-radius: 50%;
  position: relative;
  transform-origin: center;
  transition: all 0.5s;
  /* transform: rotate(-70deg); */
}
.circle.show-nav {
  transform: rotate(-90deg);
}
.circle button {
  position: absolute;
  background: transparent;
  border: 0;
  cursor: pointer;
}
.circle button:focus {
  outline: none;
}
.icon-3column {
  font-size: 40px;
  color: white;
}
.icon-close {
  font-size: 40px;
  color: white;
}
.circle button#open {
  /* background-color: #ff7979; */
  top: 55%;
  left: 50%;
}
.circle button#close {
  /* background-color: #ff7979; */
  top: 48%;
  left: 5%;
}
.content {
  max-width: 1000px;
  margin: 80px auto;
  transform-origin: top left;
  transition: all 0.5s;
  /* background-color: black; */
}
/* .content.show-nav {
  transform: rotate(-20deg);
} */
.content img {
  max-width: 100%;
}
nav {
  display: block;
  unicode-bidi: isolate;
  position: relative;
  top: 70%;
}
nav ul {
  list-style-type: none;
  padding-left: 30px;
}
nav ul li {
  transform: translate(-100%);
  transition: all 0.3s;
  margin-top: 20px;
}
nav ul li.second {
  margin-left: 20px;
}
nav ul li.third {
  margin-left: 40px;
}
nav ul.show-nav li {
  transform: translate(0);
  transition-delay: 0.3s;
}
nav ul li i.iconfont {
  font-size: 40px;
  color: white;
}
</style>
