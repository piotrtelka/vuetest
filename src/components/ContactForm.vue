<template>
  <div>
    <div class="inputs">
      <TextInput v-model="name" label="name" />
      <TextInput v-model="surname" label="surname" />
      <TextInput v-model="email" label="email" />
    </div>
    <button @click="submit">submit</button>
  </div>
</template>

<script setup>
import TextInput from "@/components/TextInput.vue";
import {ref} from "vue";

const emits = defineEmits(['submit'])

const name = ref('')
const surname = ref('')
const email = ref('')

function submit() {
    emits('submit', {
      name: name.value,
      surname: surname.value,
      email: email.value
    })

    name.value = ''
    surname.value = ''
    email.value = ''
}
</script>

<style scoped>
.inputs {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 1rem;

  min-width: 250px;
}

button {
  background-color: rgba(51, 51, 51, 0.30);
  border-radius: 8px;
  border-width: 0;
  color: #333333;
  cursor: pointer;
  padding: 10px 12px;
  text-align: center;
}
</style>