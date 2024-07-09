<script setup>
let numberX
let numberY

let calculatorModes = new Map();
calculatorModes.set("somar", numberX + numberY)
calculatorModes.set("subtrair", numberX - numberY)
calculatorModes.set("multiplicar", numberX * numberY)
calculatorModes.set("dividir", numberX / numberY)

function calculator(mode, numberX, numberY) {
    let resultado = calculatorModes.get(mode)
    return resultado
}
</script>

<template>
    <h1>Calculadora em Vue</h1>
    <div class="calculator__container">
        <div class="numbers__container">
            <form>
                <label for="number-1">X: </label>
                <input type="number" id="number-1" required placeholder="Digite o primeiro numero">
                <label for="number-2">Y: </label>
                <input type="number" id="number-2" required placeholder="Digite o segundo numero">
            </form>
        </div>

        <div class="mode__selector">
            <label for="modes">Escolha o modo</label>
            <select name="modes" id="modes">
                <option value="somar">Soma</option>
                <option value="subtrair">Subtração</option>
                <option value="multiplicar">Multiplicação</option>
                <option value="dividir">Divisão</option>
            </select>
        </div>

        <div class="result">Resultado: {{  }}</div>
    </div>
</template>

<style scoped>
h1 {
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
</style>
