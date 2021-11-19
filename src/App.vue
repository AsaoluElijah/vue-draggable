<template>
  <div class="container mt-5 mb-5">
    <div class="row">
      <div class="col mx-2 px-2 py-3 bg-light border rounded">
        <h6>Idea 💡</h6>
        <draggable
          class="draggable-list mt-3"
          :list="tasks.ideas"
          group="tasks"
        >
          <div v-for="(idea, i) in tasks.ideas" :key="i">
            <div class="bg-white mt- p-2 shadow border rounded">
              <p>{{ idea }}</p>
            </div>
          </div>
        </draggable>
      </div>
      <div class="col mx-2 px-2 py-3 bg-light border rounded">
        <h6>Todo ✍</h6>
        <draggable
          class="draggable-list mt-3"
          :list="tasks.todos"
          group="tasks"
        >
          <div v-for="(todo, i) in tasks.todos" :key="i">
            <div class="bg-white mt-2 p-2 shadow border rounded">
              <p>{{ todo }}</p>
            </div>
          </div>
        </draggable>
      </div>
      <div class="col mx-2 px-2 py-3 bg-light border rounded">
        <h6>In Progress 🗓</h6>
        <draggable
          class="draggable-list mt-3"
          :list="tasks.inProgress"
          group="tasks"
        >
          <div v-for="(task, i) in tasks.inProgress" :key="i">
            <div class="bg-white mt-2 p-2 shadow border rounded">
              <p>{{ task }}</p>
            </div>
          </div>
        </draggable>
      </div>
      <div class="col mx-2 px-2 py-3 bg-light border rounded">
        <h6>Ready to go ✅</h6>
        <draggable
          class="draggable-list mt-3"
          :list="tasks.completed"
          group="tasks"
        >
          <div v-for="(task, i) in tasks.completed" :key="i">
            <div class="bg-white mt-2 p-2 shadow border rounded">
              <p>{{ task }}</p>
            </div>
          </div>
        </draggable>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
export default {
  components: {
    draggable,
  },
  data() {
    return {
      tasks: {
        ideas: ["Migrate codebase to TypeScript"],
        todos: ["Dockerize App", "Add vue.draggable to project"],
        inProgress: ["Implement Web3 Features", "Bump to vite.js"],
        completed: [],
      },
    };
  },
};
</script>

<style scoped>
h6 {
  font-weight: 700;
}
.col {
  height: 90vh;
  overflow: auto;
}
.draggable-list {
  min-height: 10vh;
}
.draggable-list > div {
  cursor: pointer;
}
</style>
