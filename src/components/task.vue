<template>
  <div class="task-list">
    <h1 id="titulo">{{ tasks.length }} Tareas</h1>
    <form class="form" @submit.prevent="createTask">
      <label class="label" for="task">Nueva tarea:</label>
      <input class="input" type="text" v-model="newTask" id="task" />
      <input class="button" type="submit" value="Crear tarea" />
    </form>
    <ul class="list">
      <li class="task" v-for="(task, i) in tasks" :key="'task' + i" :class="{ completed: task.completed }"
        @click="completeTask(task.text)">{{ task.text }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "task_",
  data: () => ({
    newTask: "",
    tasks: []
  }),
  methods: {
    createTask() {
      let task = {
        text: this.newTask,
        completed: false
      };
      this.tasks.push(task);
      this.newTask = "";
      console.log(this.tasks);
    },
    completeTask(taskText) {
      for (let i = 0; i < this.tasks.length; i++) {
        let task = this.tasks[i];
        if (taskText === task.text) {
          task.completed = !task.completed;
        }
      }
    }
  }
};
</script>



<style scoped>
.task-list {
  width: 800px;
  max-width: 100%;
  margin: 10px auto;
}

.form {
  background: rgb(255, 255, 255);
  border-radius: 5px;
  padding: 10px;
  box-shadow: 0px 10px 22px -1px rgba(196, 207, 33, 0.25);
  margin-top: 10px;
}

.label {
  display: block;
  margin-bottom: 10px;
}

.input {
  height: 35px;
}

.button {
  margin-left: 20px;
  height: 35px;
  border: none;
  border-radius: 5px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, .2);
  background-color: #2ecc71;
  color: #ecf0f1;
  cursor: pointer
}

.list {
  margin-top: 70px;
}

.task {
  cursor: pointer;
  margin: 10px 0;
}

.completed {
  text-decoration: line-through;
  color: rgb(157, 168, 127);
}

#titulo {
  font-kerning: 0;
}
</style>
