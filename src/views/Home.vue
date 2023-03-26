<template>
  <NavBar :user="user"/>
</template>

<script lang="ts" setup>
import NavBar from "@/components/NavBar.vue";
import axios from "axios";
import {onMounted} from "vue";

let user = {}

function getUser() {
  axios.get('http://127.0.0.1:8000/api/users/1')
    .then(function (response) {
      user = response.data
      console.log(user)
      return user
    })
    .catch(function (error) {
      console.log(error);
    })
}
getUser();
</script>
