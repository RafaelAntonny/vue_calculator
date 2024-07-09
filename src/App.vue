<script setup>
import { computed, ref } from 'vue';

const x = ref(0);
const y = ref(0);
const mode = ref("somar");

const calculatorModes =  {
    somar: (x, y) => x + y,
    subtrair: (x, y) => x - y,
    multiplicar: (x, y) => x * y,
    dividir: (x, y) => x / y,
}

let resultado = computed(() => {
    let operations = calculatorModes[mode.value];
    return operations(x.value , y.value);
})

</script>

<template>
    <h1>Calculadora em Vue</h1>
    <div class="calculator__container">
        <div class="numbers__container">
            <form>
                <label for="number-1">X: </label>
                <input v-model.number="x" type="number" id="number-1" required placeholder="Digite o primeiro numero">
                <label for="number-2">Y: </label>
                <input v-model.number="y" type="number" id="number-2" required placeholder="Digite o segundo numero">
            </form>
        </div>

        <div class="mode__selector">
            <label for="modes">Escolha o modo</label>
            <select v-model="mode" name="modes" id="modes">
                <option value="somar">Soma</option>
                <option value="subtrair">Subtração</option>
                <option value="multiplicar">Multiplicação</option>
                <option value="dividir">Divisão</option>
            </select>
        </div>

        <div class="result"><p>Resultado: </p>
            {{ resultado }}
        </div>
    </div>
</template>

<style scoped>
h1, input, select {
    text-align: center;
}

div.calculator__container {
    margin: 8rem auto;
    text-align: center;
    background: #F7F5F3;
    width: 50%;
    border-radius: 8px;
}

.numbers__container, .mode__selector, .result{
    padding-top: 3rem;
}

.result {
    padding-bottom: 3rem;
}

</style>
