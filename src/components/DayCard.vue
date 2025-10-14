<template>
  <div>
    <button class="rounded-2xl bg-cyan-200 m-2 flex flex-wrap hover:scale-110">
      <card>
        <h2 class="text-xl font-bold p-4 text-center">{{ day.name }}</h2>
      </card>
    </button>
  </div>
</template>

<script setup lang="ts">
import type { WeekDay } from "@/models/WeekDay";
import { ref } from "vue";

const props = defineProps<{
  day: WeekDay;
}>();

const selectedDay = ref<boolean>(props.day.selected);
</script>
