<template>
  <v-table>
    <thead>
    <tr>
      <th class="text-left">
        Title
      </th>
      <th class="text-left">
        Description
      </th>
    </tr>
    </thead>
    <tbody>
    <tr
      v-for="task in tasks"
      :key="task.id"
    >
      <td>{{ task.title }}</td>
      <td>{{ task.description }}</td>
    </tr>
    </tbody>
  </v-table>
  <AddTask/>
</template>

<script lang="ts" setup>
import AddTask from "@/components/AddTask.vue";
import axios from "axios";

let tasks: any[] = [];

function getTasks() {
  axios.get('http://127.0.0.1:8000/api/tasks')
    .then(function (response) {

      tasks = response.data['hydra:member']
      console.log(tasks)
      return tasks
    })
    .catch(function (error) {
      console.log(error);
    })
}

getTasks();
</script>
