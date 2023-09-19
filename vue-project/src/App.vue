<script setup lang="ts">
import ChildComponent from './ChildComponent.vue';

const post = {
  id: 1,
  title: 'hosb의 vue 활용',
  mainCont: 'props와 emit 사용 방법은 ~~',
}

const receive = (newValue: string) => {
	console.log('newValue ::', newValue) // 수정한 값이 parent에게 값이 넘어옴
	post.mainCont = newValue
}
</script>

<template>
  <child-component
	:title="post.title"
    :main-cont="post.mainCont"
	@update:main-cont="receive($event)"
  />
</template>