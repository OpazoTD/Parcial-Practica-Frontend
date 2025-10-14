<template>
  <div>
    <h3 class="bold text-2xl">Gestor de dias de la semana</h3>
    <div
      v-for="dia in arrayDiasDeLaSemana"
      :key="dia.id"
      class="m-2 flex flex-wrap"
    >
      <button
        :class="[
          'bg-grey-200 b-1 p-2 rounded-xl bg-cyan-200 hover:scale-110',
          dia.selected ? 'bg-green-300' : '',
        ]"
        @click="dia.selected = !dia.selected"
      >
        {{ dia.name }}
      </button>
      <DayCard
        :day="dia"
        :selected="dia.selected"
        @click="dia.selected = !dia.selected"
        class="ml-2"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import type { WeekDay } from "@/models/WeekDay";
import { ref } from "vue";
import type { Ref } from "vue";
import DayCard from "./DayCard.vue";
const arrayDiasDeLaSemana: Ref<WeekDay[]> = ref([
  { id: 1, name: "Lunes", selected: false },
  { id: 2, name: "Martes", selected: false },
  { id: 3, name: "Miércoles", selected: false },
  { id: 4, name: "Jueves", selected: false },
  { id: 5, name: "Viernes", selected: false },
  { id: 6, name: "Sábado", selected: false },
  { id: 7, name: "Domingo", selected: false },
]);
</script>
