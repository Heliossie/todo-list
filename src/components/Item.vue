<template>
  <div>
    <div class="card my-2 item-todo">
      <p>{{ task }}</p>
      <div class="btn-supr btn btn-danger" v-on:click="deleted">X</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: ["task", "deleted"],
};
</script>

<style scoped>
.item-todo {
  position: relative;
  padding: 20px 60px 20px 30px;
  font-size: 20px;
  height: 88px;
}
.btn-supr {
  position: absolute;
  top: 10px;
  right: 10px;
}
.item-todo p {
  margin-bottom: 10px;
}
</style>