<template>
  <div>
    <div class="block">num Ref: {{ num }}</div>
    <button @click="run">点击执行run</button>
  </div>
</template>
<script>
import { ref } from '@vue/composition-api'
import { useDebounceFn } from '@xuguo/vue-hooks'
export default {
  name: 'use-debounce-fn',
  setup() {
    const num = ref(0)
    const { run } = useDebounceFn(() => {
      num.value += 1
    }, 500)
    return {
      run,
      num,
    }
  },
}
</script>
