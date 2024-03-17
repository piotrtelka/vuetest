<template>
  <div class="form-container">
    <ContactForm @submit="onSubmit" />
  </div>
  <div class="table-container">
    <ContactTable :entries="database" />
  </div>
</template>

<script setup>
import {ref} from "vue";

import ContactForm from "@/components/ContactForm.vue";
import ContactTable from "@/components/ContactTable.vue";

const database = ref([])

function onSubmit(entry) {
  // here you send data to your API and fetch it
  database.value.push(entry)
}
</script>

<style scoped>
.table-container {
  margin-left: 3rem;
}
</style>
