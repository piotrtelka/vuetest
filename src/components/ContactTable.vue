<template>
  <table>
    <tr>
      <th>name</th>
      <th>surname</th>
      <th>email</th>
    </tr>

    <tr v-for="entry in entries">
      <td>{{entry.name}}</td>
      <td>{{entry.surname}}</td>
      <td>{{entry.email}}</td>
    </tr>
  </table>
</template>

<script setup>
defineProps(['entries'])
</script>

<style scoped>
table {
  min-width: 250px;
  text-align: left;
}
</style>