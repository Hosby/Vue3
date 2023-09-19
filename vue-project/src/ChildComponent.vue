<script setup>
import { onMounted, ref } from 'vue'

const props = defineProps(['title', 'mainCont']) // ParentComponent에서 받은값
const emits = defineEmits(['update:mainCont'])

const vo = ref('')

onMounted(() => {
  vo.value = props.mainCont // vo에 받아온 props 값을 매핑함
})

</script>

<template>
  <h3> {{ props.title }} </h3>
  <textarea
    v-model="vo"
    @change="emits('update:mainCont', vo)"
  />
</template>