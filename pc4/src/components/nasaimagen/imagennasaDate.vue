<template>
  <h4>Fecha </h4>
  <div class="fecha_ini">
    <div class="q-gutter-md row items-start">
      <q-date v-model="startDate" />
    </div>
  </div>

  <div class="fecha_fin">
    <div class="q-gutter-md row items-start">
      <q-date v-model="endDate" />
    </div>
  </div>

  <div>
      <p>Fecha de inicio seleccionada: {{ startDate }}</p>
      <p>Fecha de fin seleccionada: {{ endDate }}</p>
    </div>

</template>


<script>
import { ref } from 'vue'

export default {
  setup () {
    const startDate= ref('2024/02/01')
    const endDate= ref('2024/02/01')
    return {
      startDate,
      endDate
    }
  }
}
</script>
