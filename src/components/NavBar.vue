<template>
  <v-card>
    <v-layout>
      <v-navigation-drawer
        expand-on-hover
        rail
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
            :title=userFullName
            :subtitle=user.email
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-widgets" title="tasks" value="My-tasks" to="Task"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-main style="height: 250px"></v-main>
    </v-layout>
  </v-card>
</template>

<script lang="js">
export default {
  props: ['user'],
  data() {
    return {
      userFullName: this.user.firstname + ' ' + this.user.lastname
    }
  }
}
</script>
