<script setup>
import { ref, computed } from 'vue'

const numero1 = ref(0)
const numero2 = ref(0)
const operacao = ref('+')


const resultado = computed(() => {
    const n1 = Number(numero1.value)
    const n2 = Number(numero2.value)

    switch (operacao.value) {
        case '+':
            return n1 + n2
        case '-':
            return n1 - n2
        case '*':
            return n1 * n2
        default:
            return 0
    }
})
</script>

<template>
    <div class="container">
        <h1>Calculadora VUE</h1>

        <input 
            type="number" 
            v-model="numero1" 
            placeholder="Número 1"
        >

        <select v-model="operacao">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>

        <input 
            type="number" 
            v-model="numero2" 
            placeholder="Número 2"
        >

        <h2>Resultado: {{ resultado }}</h2>
    </div>
</template>

<style scoped>
.container {
    max-width: 400px;
    margin: 40px auto;
    display: flex;
    flex-direction: column;
    gap: 12px;
    font-family: Arial;
}

input, select {
    padding: 8px;
    font-size: 16px;
}

h1 {
    text-align: center;
}
</style>