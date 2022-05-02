<template>
  <div>
    <header>
      <!-- 有值就显示要搜索的值 没值就显示 WordHount -->
      <h2 class="title">{{ wordValue ? wordValue : 'Word Hount' }}</h2>
      <div class="input-wrap">
        <input
          type="text"
          placeholder="Search a Word"
          v-model="wordValue"
          @input="$emit('update:modelValue', $event.target.value)"
        />
      </div>
    </header>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const wordValue = ref();
// 把双向绑定的值,传递给APP组件
// 如果外界使用 v-model接收 子组件必须使用update:modelValue的参数名
defineEmits(['update:modelValue']);
</script>
<style lang="scss" scoped>
header {
  height: 30vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  h2 {
    font-size: 7vw;
    font-weight: 100;
    @media (max-width: 1000px) {
      font-size: 11vw;
    }
  }
  .input-wrap {
    input {
      width: 50vw;
      border: none;
      background-color: #282c34;
      border-bottom: 1px solid rgba(197, 188, 188);
      padding: 5px;
      font-size: 18px;
      color: #fff;
      &:focus {
        outline: none;
        border-bottom: 1px solid white;
      }
      &::placeholder {
        color: rgba($color: #ffff, $alpha: 0.6);
      }
    }
  }
}
</style>
