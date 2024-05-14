<script setup>
import { reactive } from 'vue';
const estado = reactive({
    valor1: 1,
    valor2: 1,
    resultado: '',
    operacao: 'Adição'
})

function adicao() {
    const { valor1, valor2 } = estado;
    return parseFloat(valor1) + parseFloat(valor2)
}

function subtracao() {
    const { valor1, valor2 } = estado;
    return parseFloat(valor1) - parseFloat(valor2)
}

function multiplicacao() {
    const { valor1, valor2 } = estado;
    return parseFloat(valor1) * parseFloat(valor2)
}

function divisao() {
    const { valor1, valor2 } = estado;
    return parseFloat(valor1) / parseFloat(valor2)
}
</script>
<template>
    <form>
        <div class="row mb-3">
            <div class="colunas col-2">
                <input @keyup="evento => estado.valor1 = evento.target.value" type="number"
                    placeholder="Insira o primeiro valor">
            </div>
            <div class="colunas col-2">
                <select @change="evento => estado.operacao = evento.target.value" class="form-control">
                    <option value="escolha">Escolha a operação</option>
                    <option value="adicao">+</option>
                    <option value="subtracao">-</option>
                    <option value="multiplicacao">*</option>
                    <option value="divisao">/</option>
                </select>
            </div>
            <div class="colunas col-2">
                <input @keyup="evento => estado.valor2 = evento.target.value" type="number"
                    placeholder="Insira o segundo valor">
            </div>
            <div class="resultado col-2">
                <label>Resultado:</label>
            </div>
            <div class="resultado col-2">
                <p v-if="estado.operacao === 'divisao'">
                    {{ divisao() }}
                </p>
                <p v-else-if="estado.operacao === 'adicao'">
                    {{ adicao() }}
                </p>
                <p v-else-if="estado.operacao === 'subtracao'">
                    {{ subtracao() }}
                </p>
                <p v-else-if="estado.operacao === 'multiplicacao'">
                    {{ multiplicacao() }}
                </p>
            </div>
        </div>
    </form>
</template>


<style scoped>
input {
    width: 100%;
    height: 100%;
}

.resultado {
    margin: 0 auto;
    justify-content: center;
    display: flex;
    height: 100%;
}
</style>