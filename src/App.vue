<template>
  <p>{{unreactive_count}}</p>
  <button @click="unreactive_count++">Increment (Won't work)</button>

  <p>{{count}}</p>
  <button @click="count++">Increment</button>

  <p>{{double_count}}</p>
  <button @click="double">Double</button>
</template>

<script>
import { ref } from 'vue'

export default {
  name: "App",

  setup() {
    let unreactive_count = 0;
    let count = ref(0);
    let double_count = ref(1);

    function double() {
      double_count.value *= 2;
    }

    return {
      unreactive_count,
      count,
      double_count,
      double,
    };
  }
}
</script>
