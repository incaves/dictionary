<template>
  <div class="container">
    <main>
      <!-- 接受Header子组件传递的数据 可以使用 v-model来接收 -->
      <Header v-model="searchWord" />
      <!-- 再传递给Defintion -->
      <Defintion :searchWord="searchWord" />
    </main>
  </div>
</template>
<script setup>
import Header from './components/Header.vue';
import Defintion from './components/Defintion.vue';
import { ref } from 'vue';
const searchWord = ref();
</script>
<style lang="scss" scoped>
$text-color: white;
div.container {
  height: 100vh;
  overflow: hidden;
  background-color: #282c34;
  main {
    max-width: 1000px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    color: $text-color;
    padding: 1rem;
  }
}
</style>
