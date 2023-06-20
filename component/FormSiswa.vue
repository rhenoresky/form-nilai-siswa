<template>
  <form v-on:submit.prevent="clickTambahSiswa">
    <label for="nomer">Nomer Induk Siswa</label>
    <input v-model="nomer" id="nomer" name="nomer" type="text">
    <label for="nama">Nama siswa</label>
    <input v-model="nama" id="nama" name="nama" type="text">
    <label for="nilai">Nilai Tugas</label>
    <input v-model="nilai" id="nilai" name="nilai" type="text">
    <button type="submit">Submit</button>
  </form>
</template>

<script setup>
const emit = defineEmits(['tambah'])
const nomer = ref('')
const nama = ref('')
const nilai = ref('')
const data = reactive({
  nomer,
  nama,
  nilai
})

function clickTambahSiswa() {
  if (nomer.value.length > 0 && nama.value.length > 0 && nilai.value.length > 0 && Boolean(Number(nilai.value)) != false) {
    emit('tambah', data)
    nomer.value = ''
    nama.value = ''
    nilai.value = ''
  }
}
</script>