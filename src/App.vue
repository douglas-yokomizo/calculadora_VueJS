<script lang="ts">
export default {
  name: 'App',
  data() {
    return {
      
      primeiroNumero: 0,
      segundoNumero: 0,
      operacao: 'Escolha uma operação',
      resultado: 0
    }
  },
  methods: {
    somar(primeiroNumero: number, segundoNumero: number) {
      const resultado = (primeiroNumero + segundoNumero)
      this.resultado = resultado
      return resultado
    },
    subtrair(primeiroNumero: number, segundoNumero: number) {
      const resultado = (primeiroNumero - segundoNumero)
      this.resultado = resultado
      return resultado
    },
    multiplicar(primeiroNumero: number, segundoNumero: number) {
      const resultado = (primeiroNumero * segundoNumero)
      this.resultado = resultado
      return resultado
    },
    dividir(primeiroNumero: number, segundoNumero: number) {
      const resultado = (primeiroNumero / segundoNumero)
      this.resultado = resultado
      return resultado
    },
    calcular() {
      const operacaoSelecionada = this.operacao

      switch (operacaoSelecionada) {
        case "somar":
          return this.resultado = this.somar(this.primeiroNumero, this.segundoNumero)
        case "subtrair":
          return this.resultado = this.subtrair(this.primeiroNumero, this.segundoNumero)
        case "multiplicar":
          return this.resultado = this.multiplicar(this.primeiroNumero, this.segundoNumero)
        case "dividir":
          return this.resultado = this.dividir(this.primeiroNumero, this.segundoNumero)
        default:
          return "Operação inválida"
      }
    }
  }
}
</script>

<template >

  <header>
    <h1>
      Calculadora com Vue JS
    </h1>
  </header>

  <main>
    <label>
      <strong>Escolha uma operação</strong>
      <select v-model="operacao" class="operacoes">
        <option value="somar">Somar</option>
        <option value="subtrair">Subtrair</option>
        <option value="dividir">Dividir</option>
        <option value="multiplicar">Multiplicar</option>
      </select>
    </label>
    <form class="formulario">
      <label>
        <h4>Primeiro Número</h4>
        <input type="number" v-model=primeiroNumero>
      </label>
      <label>
        <h4>Segundo Número</h4>
        <input type="number" v-model=segundoNumero>
      </label>
    </form>
    <h3>Resultado: {{ calcular() }}</h3>
  </main>
</template>

<style>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

header {
  margin-bottom: 5rem;
}

main {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  background-color: beige;
  padding: 4rem 2rem;
  box-shadow: 10px 10px rgba(0, 0, 0, 0.1);
  border-radius: 15%;
}

.formulario {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

label {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

input {
  width: 80px;
  padding: .15rem;
  text-align: right;
}

button {
  width: 100%;
  padding: .5rem;
  background-color: transparent;
  font-size: large;
}

button:hover{
  cursor: pointer;
  scale: 1.1;
  transition: 300ms;
  animation: ease-in-out;
  transform: translateY(-.2rem);
  box-shadow: 5px 5px rgba(0, 0, 0, 0.1);
}

</style>