<template>
	<div>
	  <p v-text="message"></p>
	  <p v-bind:style="dynamicStyle">{{ message }}</p>
	  <input v-model="message" />
	  <p v-if="isVisible">This is visible!</p>
	  <ul>
		<li v-for="(item, index) in items" :key="index">{{ item }}</li>
	  </ul>
	  <button @click="toggleVisibility">Toggle Visibility</button>
	</div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const message = ref('Hello Vue.js!');
  const isVisible = ref(true);
  const items = ref(['Item 1', 'Item 2', 'Item 3']);
  
  // Dynamischer Style abhängig vom message-Wert
  const dynamicStyle = computed(() => {
	return {
	  color: message.value.includes('Vue') ? 'green' : 'black',
	};
  });
  
  function toggleVisibility() {
	isVisible.value = !isVisible.value;
  }
  </script>
  