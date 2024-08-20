<template>
	<div>
	  <h1>{{ message }}</h1>
	  <button @click="reverseMessage">Reverse Message</button>
	  
	  <h2>Reactive Object Example:</h2>
	  <p>{{ person.name }} - {{ person.age }} years old</p>
	  <button @click="updatePerson">Update Person</button>
	</div>
  </template>
  
  <script setup>
  import { ref, reactive } from 'vue';
  
  // Verwenden von ref für einfache Daten
  const message = ref('Hello Vue.js!');
  
  // Verwenden von reactive für komplexe Datenstrukturen
  const person = reactive({
	name: 'Loris Galler',
	age: 23
  });
  
  // Funktion zum Umkehren der Nachricht
  function reverseMessage() {
	message.value = message.value.split('').reverse().join('');
  }
  
  // Funktion zum Aktualisieren des reaktiven Objekts
  function updatePerson() {
	person.name = 'Galler Loris';
	person.age = 42;
  }
  </script>
  