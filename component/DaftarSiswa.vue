<template>
  <FormSiswa @tambah="tambahSiswa" />
  <table border="1">
    <tr>
      <th>No</th>
      <th>Nomer Induk Siswa</th>
      <th>Nama Siswa</th>
      <th>Nilai Tugas</th>
    </tr>
    <tr v-for="(item, i) in siswa" :key="i">
      <td>{{ i + 1 }}</td>
      <td>{{ item.nomer }}</td>
      <td>{{ item.nama }}</td>
      <td>{{ item.nilai }}</td>
    </tr>
    <tr>
      <td colspan="3">Nilai Rata - Rata</td>
      <td>{{ average }}</td>
    </tr>
  </table>
</template>

<script setup>
import FormSiswa from './FormSiswa.vue'
let siswa = reactive([
  {
    nomer: '1213141516',
    nama: 'Uchiha Feri',
    nilai: 97
  },
  {
    nomer: '1213232425',
    nama: 'Abdul Alok',
    nilai: 86
  }
])

const total = computed({
  get() {
    let jumlah = 0
    siswa.map((item) => {
      jumlah += item.nilai
    })
    return jumlah
  }
})

const average = computed(() => total.value / siswa.length)

function tambahSiswa(data) {
  siswa.push({
    nomer: data.nomer,
    nama: data.nama,
    nilai: Number(data.nilai),
  })
}
</script>