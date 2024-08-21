<template>
	<div>
	  <h1>Parent Component</h1>
	  <!-- Übergabe der initialen Nachricht als Prop an das Kind -->
	  <ChildComponent :initialMessage="parentMessage" @message-reversed="handleReversedMessage" />
	  <p>Reversed Message from Child: {{ reversedMessage }}</p>
	</div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import ChildComponent from './childComponent.vue';
  
  const parentMessage = ref('Hello from Parent!');
  const reversedMessage = ref('');
  
  // Funktion zum Handhaben des Events, das vom Kind ausgesendet wird
  function handleReversedMessage(reversed) {
	reversedMessage.value = reversed;
  }
  </script>
  