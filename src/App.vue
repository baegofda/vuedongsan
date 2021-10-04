<template>
  <Modal
    @close="isOnModal = $event"
    :isOnModal="isOnModal"
    :contents="contents"
    :clickId="clickId"
  />
  <input type="text" v-model="text" />
  <Discount />
  <!-- $emit -->
  <Card
    :contents="contents"
    @openModal="
      isOnModal = true;
      clickId = $event;
    "
  />
</template>

<script>
import data from "./data/post";
import Discount from "./components/Discount.vue";
import Modal from "./components/Modal.vue";
import Card from "./components/Card.vue";

export default {
  name: "App",
  // 데이터는 여기
  data() {
    return {
      //state
      text: "",
      clickId: 0,
      isOnModal: false,
      contents: data,
    };
  },
  watch: {
    text() {
      console.log("aaa");
    },
  },
  methods: {
    report() {
      this.reportCount++;
    },
  },
  components: { Discount, Modal, Card },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
