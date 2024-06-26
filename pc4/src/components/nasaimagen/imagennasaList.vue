<template>
  <div class="imgnasa-list">
    <q-card v-for="item in apodItems" :key="item.date">
      <q-card-section>
        <q-img :src="item.url" :alt="item.title" />
      </q-card-section>
      <q-card-section>
        <q-card-title>{{ item.title }}</q-card-title>
        <q-card-main>{{ item.explanation }}</q-card-main>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import { ref, watch } from 'vue';
import axios from 'axios';



export default {
  props: {
    startDate: {
      type: String,
      required: true
    },
    endDate: {
      type: String,
      required: true
    }
  },
  setup(props) {
    const apodItems = ref([]);

    // Vigila los cambios en startDate y endDate
    watchEffect(() => {
      fetchAPOD(props.startDate, props.endDate);
    });

    const fetchAPOD = async (startDate, endDate) => {
      try {
        const response = await axios.get('https://api.nasa.gov/planetary/apod', {
          params: {
            api_key: '16nGRIogYbQzfjEwstOvz02dKzmT7yXnPclzMO32',
            start_date: startDate,
            end_date: endDate
          }
        });
        apodItems.value = response.data;
      } catch (error) {
        console.error('Error al consultar la API de NASA APOD:', error);
      }
    };

    return {
      apodItems
    };
  }
};
</script>

<style scoped>
/* Estilos específicos si es necesario */
</style>
