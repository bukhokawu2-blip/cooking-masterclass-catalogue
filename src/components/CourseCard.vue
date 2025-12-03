<template>
  <div class="card">
    <h2>{{ title }}</h2>
    <p>Chef: {{ chef }}</p>
    <p>Level: {{ level }}</p>
    <p>Price: R{{ price }}</p>

    <p v-if="soldOut" style="color:red; font-weight:bold;">
      SOLD OUT
    </p>

    <button 
      :disabled="soldOut"
      @click="$emit('saveCourse')"
    >
      Save to Wishlist
    </button>
  </div>
</template>

<script>
export default {
  name: "CourseCard",
  props: ['title', 'chef', 'price', 'level', 'soldOut']
}
</script>

<style>
.card {
  border: 1px solid lightgray;
  padding: 15px;
  margin: 10px 0;
  border-radius: 6px;
}
button {
  padding: 6px 10px;
  cursor: pointer;
}
button:disabled {
  background: lightgray;
  cursor: not-allowed;
}
</style>
