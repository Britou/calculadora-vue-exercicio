<script>
    export default {
        data () {
            return {
                num1: 0,
                num2: 0,
                operacao: '+',
                resultado: 0
            }
        },
        computed: {
            resultado () {
                if (this.operacao === "+") {
                    return this.num1 + this.num2
                } else if (this.operacao === "-") {
                    return this.num1 - this.num2
                } else if (this.operacao === "*") {
                    return this.num1 * this.num2
                } else if (this.operacao === "/") {
                    if (this.num2 === 0) {
                        return "Divisão por zero"
                    }
                    return this.num1 / this.num2
                }
            }
        }
    }

</script>

<template>
    <div class="calculadora">
        <h1>Calculadora</h1>

        <input type="number" v-model="num1" />
        <input type="number" v-model="num2" />

        <select v-model="operacao">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>

        <p class="resultado">Resultado: {{ resultado }}</p>
    </div>
</template>
<style>
.calculadora {
    max-width: 320px;
    margin: 50px auto;
    padding: 30px;
    background: #1e1e1e;
    border-radius: 12px;
    color: #fff;
    font-family: Arial, sans-serif;
    text-align: center; /* centraliza horizontalmente */
    display: flex;
    flex-direction: column; /* empilha os elementos verticalmente */
    gap: 15px; /* espaçamento consistente entre elementos */
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
}

.calculadora h1 {
    font-size: 26px;
    margin: 0 auto 10px auto; /* centraliza o título */
}

.calculadora input,
.calculadora select {
    width: 100%; /* força todos os elementos a terem mesma largura */
    padding: 12px 10px;
    font-size: 18px;
    border-radius: 8px;
    border: none;
    outline: none;
    box-sizing: border-box; /* importante para largura consistente */
}

.calculadora input {
    background: #2c2c2c;
    color: #0f0;
}

.calculadora select {
    background: #444;
    color: #fff;
}

.resultado {
    font-size: 22px;
    font-weight: bold;
    color: #0f0;
    margin-top: 10px;
}
</style>