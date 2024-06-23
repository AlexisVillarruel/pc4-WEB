<template>
  <div class="imgnasa-page">
    <div class="filtro-fecha">
      aqui va el filtro-fecha
      <imagennasaDate />
    </div>
    <div class="imgnasa-list">
      aqui va la lista
      <imagennasaList />
    </div>
  </div>
</template>

<style>
.imgnasa-page {
  display: flex;
  justify-content: space-between;
 }

 .filtro-fecha {
  width: 25%;
 }

 .imgnasa-list{
  width: 75%;
 }
</style>

<script>
import imagennasaDate from 'src/components/nasaimagen/imagennasaDate.vue';
import imagennasaList from 'src/components/nasaimagen/imagennasaList.vue';

export default {
  name: "NasaimgPage",
  components: {
    imagennasaDate,
    imagennasaList,
  }
}
</script>
