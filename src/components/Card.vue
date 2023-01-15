<script setup>

import { defineProps } from 'vue';

const { quiz } = defineProps(['quiz'])


</script>



<template>
    <div class="card">
        <img :src="quiz.img" :alt="quiz.name" />
        <div class="card-text">
            <h2>{{ quiz.name }}</h2>
            <p>{{ quiz.questions.length }} questions</p>
        </div>
    </div>
</template>



<style scoped>
.card {
    width: 180px;
    overflow: hidden;
    box-shadow: 1px 1px 10px rgba(1, 1, 1, 0.1);
    cursor: pointer;
}

.card-text {
    padding: 0.50rem;
}

.card-text h2 {
    font-weight: 600;
}

.card img {
    width: 100%;
    height: 125px;
}
</style>




