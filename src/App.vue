<script setup lang="ts">
import { ref } from "vue";

const periods = ["Aujourd'hui", "Cette semaine", "Ce mois"];

let selectedPeriod = ref("Aujourd'hui");

function selectPeriod(period: string) {
    console.log(period);
    selectedPeriod.value = period;
}
</script>

<template>
    <nav>
        <span>
            <a
                href="#"
                v-for="period of periods"
                v-bind:key="period"
                v-bind:class="{ 'bg-primary': selectedPeriod === period }"
                v-on:click="selectPeriod(period)"
            >
                {{ period }}
            </a>
        </span>
    </nav>
    {{ selectedPeriod }}
</template>

<style scoped>
nav a {
    margin: 0 10px;
    padding: 5px;
    border-radius: 3px;
    color: inherit;
    text-decoration: none;
}

nav a.bg-primary {
    color: white;
}
</style>
