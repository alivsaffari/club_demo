<script setup lang="ts">
const club_name = defineModel('club_name')
</script>

<template>
  <form class="establish_form" action="">
    <h1>🏆</h1>
    <h1>Establish Your Club!</h1>
    <input
      type="text"
      class="form-control"
      id="club_name"
      v-model="club_name"
      placeholder="Club Name"
    />
    <button class="btn btn-primary">Let's Start!</button>
  </form>
</template>

<style scoped>
.establish_form {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 10px;
  height: 100vh;
}

input {
  max-width: 50%;
}
</style>
