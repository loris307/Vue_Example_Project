<template>
	<div>
	  <h2>Child Component</h2>
	  <p>Message from Parent: {{ message }}</p>
	  <button @click="reverseMessage">Reverse Message</button>
	</div>
  </template>
  
  <script setup>
  // Empfang der initialen Nachricht als Prop
  import { defineProps, ref } from 'vue';
  
  const props = defineProps({
	initialMessage: String,
  });
  
  // Reaktive Variable zur Speicherung der Nachricht
  const message = ref(props.initialMessage);
  
  // Funktion zum Umkehren der Nachricht und Senden des Events
  function reverseMessage() {
	const reversed = message.value.split('').reverse().join('');
	// Auslösen eines benutzerdefinierten Events 'message-reversed' mit der umgekehrten Nachricht als Payload
	emit('message-reversed', reversed);
  }
  </script>
  