<template>
  <div class="card">
    <DaftarSiswa />
  </div>
</template>

<script setup>
import DaftarSiswa from './component/DaftarSiswa.vue'
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #3A3845;
  color: #F7CCAC;
}

.card {
  display: flex;
  justify-content: center;
  gap: 48px;
  width: 100%;
  margin-top: 18px;
  height: auto;
}

.card form {
  display: flex;
  flex-direction: column;
  width: 20%;
}

.card table {
  width: 70%;
  border-collapse: collapse;
  height: auto;
  border-color: #C69B7B;
}

.card table tr {
  height: 56px;
  text-align: center;
}

.card form label {
  margin-bottom: 2px;
}

.card form input {
  margin-bottom: 8px;
  height: 28px;
  border: 1px solid #C69B7B;
  outline: none;
  border-radius: 2px;
  color: #3A3845;
  padding: 0px 3px;
}

.card form button {
  width: 40%;
  background-color: #826F66;
  border: 1px solid #C69B7B;
  color: #F7CCAC;
  padding: 10px 0px;
  margin: auto;
  margin-top: 12px;
  border-radius: 4px;
}

.card form button:hover {
  background-color: #C69B7B;
}

</style>
