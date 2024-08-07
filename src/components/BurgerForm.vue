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
          <option
            v-for="bread in breadOptions"
            :value="bread.id"
            v-bind:key="bread.id"
          >
            {{ bread.tipo }}
          </option>
        </select>
      </div>
      <div class="input-container">
        <label for="protein">Selecione a proteína</label>
        <select name="protein" id="protein" v-model="protein">
          <option
            v-for="protein in proteinOptions"
            :value="protein.id"
            v-bind:key="protein.id"
          >
            {{ protein.tipo }}
          </option>
        </select>
      </div>
      <div id="optionals" class="input-container">
        <span id="optionals-title">Selecione os opcionais</span>
        <div
          class="checkbox-container"
          v-for="opt in fetchedOptionals"
          v-bind:key="opt.id"
        >
          <input type="checkbox" :name="opt.id" :id="opt.id" />
          <label class="optional-label" :for="opt.id">{{ opt.tipo }}</label>
        </div>
      </div>
      <div class="input-container">
        <input type="submit" class="submit-btn" value="Criar meu Burguer!" />
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "BurgerForm",
  data() {
    return {
      breadOptions: null,
      proteinOptions: null,
      fetchedOptionals: null,
      customerName: "",
      bread: null,
      protein: null,
      optionals: [],
      status: "Solicitado",
      message: null,
    };
  },

  methods: {
    async getIngredients() {
      const request = await fetch("http://localhost:3000/ingredientes");
      const data = await request.json();

      this.breadOptions = data.paes;
      this.proteinOptions = data.carnes;
      this.fetchedOptionals = data.opcionais;
    },
  },

  mounted() {
    this.getIngredients();
  },
};
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

label:not(.optional-label),
#optionals-title {
  font-weight: bold;
  margin-bottom: 15px;
  color: #222;
  padding: 5px 10px;
  border-left: 4px solid #fcba03;
}

.optional-label {
  margin-left: 0.5em;
  font-weight: bold;
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
  justify-content: flex-start;
  align-items: center;
  width: 50%;
  margin-bottom: 20px;
}
.checkbox-container label,
.checkbox-container input {
  width: auto;
}

.submit-btn {
  background-color: #222;
  color: #fcba03;
  font-weight: bold;
  border: 2px solid #222;
  padding: 10px;
  margin: 0 auto;
  cursor: pointer;
  transition: 0.2s all;
}

.submit-btn:hover {
  background-color: #fcba03;
  color: #222;
}
</style>
