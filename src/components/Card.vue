<template>
  <div v-for="content in contents" :key="content.id">
    <img :src="content.image" alt="sss" />
    <h4 @click="$emit('openModal', content.id)">
      {{ content.title }}
    </h4>
    <p>{{ content.content }}</p>
    <p>{{ content.price }} 만원</p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    contents: Array,
  },
};
</script>

<style></style>
