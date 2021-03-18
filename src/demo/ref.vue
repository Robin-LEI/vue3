<template>
  <div>
    <h1>{{count}}</h1>
    <button @click="click">click add</button>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  name: 'App',
  setup() {
    let count = ref(0);

    const click = () => {
      count.value++
    }
    return {
      count,
      click
    }
  },
}
</script>
