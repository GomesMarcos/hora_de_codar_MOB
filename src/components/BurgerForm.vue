<template>
  <div>
    <p>componente de mensagem</p>
    <form action="" id="burger-form">
      <div class="input-container">
        <label for="name">Nome do cliente</label>
        <input
          type="text"
          id="name"
          name="name"
          v-model="name"
          placeholder="Digite seu nome"
        />
      </div>
      <div class="input-container">
        <label for="bread">Selecione o pão</label>
        <select name="bread" id="bread" v-model="bread">
          <option value="0">Integral</option>
        </select>
      </div>
      <div class="input-container">
        <label for="protein">Selecione a proteína</label>
        <select name="protein" id="protein" v-model="protein">
          <option value="0">Patinho</option>
        </select>
      </div>
      <div class="input-container">
        <label>Selecione os opcionais</label>
        <div class="checkbox-container">
          <span for="salame">Salame</span>
          <input type="checkbox" name="salame" id="salame" />
        </div>
      </div>
      <div class="input-container">
        <input type="submit" class="submit-btn" value="Confirmar" />
      </div>
    </form>
  </div>
</template>

<script>
export default {};
</script>

<style>
#burger-form {
  max-width: 400px;
  margin: 0 auto;
}

.input-container {
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}

label {
  font-weight: bold;
  margin-bottom: 15px;
  color: #222;
  padding: 5px 10px;
  border-left: 4px solid #fcba03;
}

input,
select {
  padding: 5px 10px;
  width: 300px;
}

#optionals {
  flex-direction: row;
  flex-wrap: wrap;
}

.checkbox-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 50%;
  margin-bottom: 20px;
}
</style>
