<template>
  <div id="app">
    <div class="list">
      <h2>id</h2>
      <h2>Task Description</h2>
      <h2>Completo</h2>
    </div>
    <div class="bucket-list" v-for="task in tasks" v-bind:key="task.id">
      <span v-if="task.isCompleted" class="textHash">
        <p class="listItem">{{ task.id }}</p>
        <p class="listItem">{{ task.description }}</p>
        <p class="listItem">{{ task.isCompleted }}</p>
      </span>
      <span v-else v-bind:style="{ textDecoration: lineThrough }">
        <p class="listItem">{{ task.id }}</p>
        <p class="listItem">{{ task.description }}</p>
        <p class="listItem">{{ task.isCompleted }}</p>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      tasks: [
        { id: 1, description: "Go to grocery store", isCompleted: false },
        { id: 2, description: "Dentist Apointment", isCompleted: false },
        { id: 3, description: "Homework", isCompleted: true },
        {
          id: 4,
          description: "Send happy birthday to professor",
          isCompleted: true,
        },
        { id: 5, description: "Call Marcia", isCompleted: false },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 10%;
  margin-left: 20%;
}
.list {
  width: 50%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.bucket-list {
  width: 50%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
span {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.textHash {
  text-decoration: line-through;
  color: green;
}
</style>