
<script setup>
import { ref, watch } from 'vue';
import q from '../data/quiz.json'
import Card from '../components/Card.vue'

const quizes = ref(q);
const search = ref("");

watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})

</script>

<template>
    <main>
        <div class="container">
            <header>
                <h1>Quizzes</h1>
                <input type="text" placeholder="search . . ." v-model.trim="search" />
            </header>

            <div class="options-wp">
                <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
            </div>
        </div>
    </main>
</template>



<style scoped>
header {
    margin: 5rem 0;
    display: flex;

    align-items: center;
}

h1 {
    font-weight: bold;
    margin-right: 2rem;

}

input {
    border: none;
    border-radius: 20px;
    background-color: antiquewhite;
    padding: 0.75rem;
}

.container {
    max-width: 70%;
    margin: 0 auto;
}

.options-wp {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
}
</style>