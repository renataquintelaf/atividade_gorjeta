<script setup>
import { ref } from "vue";
const pessoas = ref("");
const valor = ref("");
const gorgeta = ref("");
</script>
<template>
  <div class="container">
    <h1> Gorjeta</h1>
    <input type="number" v-model="valor" placeholder="Valor da conta" />

    <select name="" id="Avaliação" v-model="gorgeta">
      <option value="1" selected="selected">
        Selecione a avaliação do atendimento:
      </option>
      <option value="05">5% (Péssimo)</option>
      <option value="10">10% (Ruim)</option>
      <option value="15">15% (Ok)</option>
      <option value="20">20% (Bom)</option>
      <option value="25">25% (Muito bom)</option>
      <option value="30">30% (Excepcional)</option>
    </select>

    <input type="number" placeholder="Pessoas à pagar" v-model="pessoas" />

    <p>
      
      Valor à ser pago: R$
      {{ Math.ceil(((valor * gorgeta) / pessoas) * 100) / 100 }}
    </p>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');

.container {
  margin: 100px auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: 1px transparent;
  border-radius: 15px;
  width: 600px;
  height: 500px;
  background-color: #AC7088;

}
input,
select,
p {
  margin: 20px;
  width: 280px;
  height: 45px;
  border-radius: 25px;
   border: 1px solid transparent;
}
p {
  border: 1px solid transparent;
  padding: 2px 6px;
  background-color: white;
}
body {
  height: 665px;
  
}
*{
  font-family: 'Pacifico', cursive;
  font-weight: 100px;

}
.template {
  background-color: #DEB6AB;
}
</style>