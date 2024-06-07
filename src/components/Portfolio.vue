<template>
  <div class="portfolio">
    <h1>Welcome to Dindra Desvantio Web</h1>
    <p>Ini Web Sederhana Yang Saya Buat</p>
    <p>Mohon Maaf Apabila Masih Banyak Kekurangan</p>
    <p>Semua Yang saya Buat Disini Cuma Sebagai Contoh Tugas Saja</p>
    <slot></slot>
  </div>
</template>

<script>
export default {
};
</script>

<style>
.portfolio {
  padding: 40px 20px;
  background: linear-gradient(120deg, #333333 0%, #444444 100%);
  color: #ffdd57;
  text-align: center;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

.portfolio h1 {
  font-size: 2.5em;
  margin-bottom: 20px;
  color: #ffdd57;
}

.portfolio p {
  font-size: 1.2em;
  margin-bottom: 20px;
  color: #ffffff;
}
</style>
