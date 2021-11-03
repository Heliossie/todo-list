<template>
  <div class="container mt-5">
    <h1>Rentrez des choses à faire</h1>
    <form>
      <div class="form-group">
        <label for="action">Action</label>
        <input
          v-model="formData.task"
          type="text"
          id="action"
          class="form-control"
        />
      </div>
      <button v-on:click.prevent="creatItem" class="btn btn-primary mb-3">
        Créer une tâche
      </button>
    </form>

    <ul>
      <li v-bind:key="index" v-for="(task, index) in tableTask">
        <item v-bind:id="index" :task="task" :deleted="deleted"></item>
      </li>
    </ul>
  </div>
</template>

<script>
import Item from "./Item.vue";

export default {
  name: "Contenu",
  data() {
    return {
      formData: {
        task: "",
      },
      tableTask: [
        "Faire à manger",
        "Enmener la voiture au garage",
        "Apprendre Vue.JS",
      ],
    };
  },
  methods: {
    creatItem: function () {
      this.tableTask.push(this.formData.task);
      this.formData.task = "";
    },
    deleted: function (e) {
      this.tableTask.splice(e.target.parentNode.id, 1);
    },
  },
  components: { item: Item },
};
</script>

<style>
h1 {
  margin-top: 100px !important;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>