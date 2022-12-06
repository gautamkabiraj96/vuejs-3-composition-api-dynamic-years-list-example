<script setup>
import { ref, onMounted } from 'vue'

const yearsList = ref([])
const selectedYear = ref(null)

const getYearsList = () => {
    const startYear = 1990;
    const endYear = new Date().getFullYear();
    for (let i = endYear; i >= startYear; i--) {
        yearsList.value = [...yearsList.value, i]
    }
}

onMounted(() => {
  getYearsList()
})

</script>

<template>
<div>
    <h1>
      Years list
    </h1>
    <p>
      <select v-model="selectedYear">
        <option v-for="(year, y) in yearsList" :key="y" :value="year">
          {{year}}
        </option>
      </select>
    </p>
    <p>
      Selected year: {{selectedYear}}
    </p>
</div>
</template>