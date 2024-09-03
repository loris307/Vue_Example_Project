<template>
	<div>
	  <h2>Child Component</h2>
	  <p>Message from Parent: {{ message }}</p>
	  <button @click="reverseMessage">Reverse Message</button>
	</div>
  </template>
  
  <script setup>
  import { defineProps, ref } from 'vue';
  
  const props = defineProps({
	initialMessage: String,
  });
  
  const message = ref(props.initialMessage);
  
  // Destructure the `emit` function from the setup context
  const emit = defineEmits(['message-reversed']);
  
  function reverseMessage() {
	const reversed = message.value.split('').reverse().join('');
	emit('message-reversed', reversed);
  }
  </script>
  
  