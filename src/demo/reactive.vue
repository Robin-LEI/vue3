<template>
  <div>
    <ul>
      <li v-for="(item, index) in state.arr" :key="index" @click="remove(index)">
        {{item.name}}
      </li>
    </ul>
  </div>
</template>
<script>
import {reactive} from 'vue'
function renderArr() {
  let state = reactive({
    arr: [{ name: 'robin', id: 1 },{ name: 'dana', id: 2 }]
  });
  const remove = (idx) => {
    state.arr = state.arr.filter((item, index) => index !== idx);
  }
  return {
    state,
    remove
  }
}
export default {
  setup() {
    return {
      ...renderArr()
    }
  },
}
</script>