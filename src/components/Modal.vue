<template>
  <div class="black-bg" v-if="isOnModal">
    <div class="white-bg">
      <h4>{{ contents[clickId].title }}</h4>
      <p>{{ contents[clickId].content }}</p>
      <p>{{ contents[clickId].price }} 만원</p>
      <p @click="$emit('close', false)">닫기</p>
      <Discount />
    </div>
  </div>
</template>

<script>
import Discount from "./Discount.vue";
export default {
  name: "Modal",
  props: {
    contents: Array,
    clickId: Number,
    isOnModal: Boolean,
  },
  components: {
    Discount,
  },
};
</script>

<style></style>
