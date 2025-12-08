<template>
    <div class="main-container">
        
        <p>Pedido Realizado com sucesso!</p>
        <div>
          <form id="Bottle-form">
            <div class="input-container">
              <label for="name">Nome:</label>
              <input type="text" id="name" name="name" v-model="nome" placeholder="Digite seu nome"/>
            </div>
            <div class="input-container">
              <label for="BottleBody">Escolha o corpo da garrafa</label>
              <select name="BottleBody" id="BottleBody" v-model="BottleBody">
                <option value="">Selecione a estrutura da sua garrafa de preferência</option>
                <option v-for="body in BottleBodies" :key="body.id" :value="body.tipo">{{body.tipo}}</option>
              </select>
            </div>
               <div class="input-container">
              <label for="BottleNameTag">Escolha a sua frase(Max: 16 caracteres)</label>
              <input type="text" placeholder="Sua frase aqui" maxlength="16" v-model="BottleNameTag">
            </div>
             <div class="input-container">
              <label for="BottleNameTagSize">Escolha o tamanho do texto</label>
              <select name="BottleNameTagSize" id="BottleNameTagSize" v-model="BottleNameTagSize">
                <option value="">Selecione o tamanho da fonte</option>
                <option v-for="size in BottleNameTagSizes" :key="size.id" :value="size.tipo">{{size.tipo}}</option>
              </select>
            </div>
             <div class="input-container">
              <label for="BottleNameTagType">Escolha a tipografia do texto</label>
                <select name="BottleNameTagType" id="BottleNameTagType" v-model="BottleNameTagType">
                <option value="">Selecione a tipografia da fonte</option>
                <option value="Arial, sans-serif">Arial</option>
                <option value="'Times New Roman', Times, serif">Times New Roman</option>
                <option value="Georgia, serif">Georgia</option>
                <option value="'Courier New', Courier, monospace">Courier New</option>
                <option value="Verdana, Geneva, sans-serif">Verdana</option>
                <option value="'Trebuchet MS', Helvetica, sans-serif">Trebuchet MS</option>
                <option value="Roboto, 'Helvetica Neue', Arial, sans-serif">Roboto</option>
                <option value="Montserrat, 'Helvetica Neue', Arial, sans-serif">Montserrat</option>
                <option value="Lora, 'Times New Roman', serif">Lora</option>
                <option value="Helvetica, Arial, sans-serif">Helvetica</option>
              </select>
            </div>
           
            <div id="OptionalsContainer" class="input-container">
              <Label id="OptionalTittle" for="Optional">Selecione os opcionais</label>
                <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                  <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.tipo">
                  <span>{{ opcional.tipo }}</span>

                </div>

            </div>
            <div class="input-container">
              <input type="submit" class="submit-btn" value="Criar a minha garrafa">
            </div>
          </form>
        </div>
    </div>
</template>
<script>

export default {
  name: 'BottleForm',
  data(){
    return {
      BottleBodies: null,
      BottleNameTags: null,
      BottleNameTagSizes: null,
      BottleNameTagTypes: null,
      BottleBody: null,
      BottleNameTag: null,
      BottleNameTagSize: null,
      BottleNameTagType: null,
      nome: null,
      opcionais: [],
      status: 'Solicitado',
      message: null

    }
  },
  methods: {
    async getRequests(){
      const requestFetch = await fetch('http://localhost:3000/Body');
      const dataFromJason = await requestFetch.json();
      this.BottleBodies = dataFromJason.BottleBodies;
      this.BottleNameTags = dataFromJason.BottleNameTags;
      this.BottleNameTagSizes = dataFromJason.BottleNameTagSizes;
      this.opcionaisdata = dataFromJason.opcionais;

    }
  },
  mounted () {
    this.getRequests();
  }
};
</script>

<style scoped>
  #Bottle-form {
    max-width: 400px;
    margin: 0 auto;
  }

  .input-container {
    margin-bottom: 15px;
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  }

  label {
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #FCBA03;
  }

  input, select {
    padding: 5px 10px;
    width: 300px;
  }
  .optional-container {
    flex-direction: row;
    flex-wrap: wrap;
  }

  #OptionalColor {
    width: 100%;
  }

  .checkbox-container {
    display: flex;
    gap: 10px;
    align-items: flex-start;
    margin-bottom: 20px;
    width: 50%;
  }

  .checkbox-container span,
  .checkbox-container input {
    width: auto;
    cursor: pointer;
  }

  .checkbox-container span {
    margin-left: 6px;
    font-weight: bold;
  }

  .submit-btn {
    background-color: #FCBA03;
    color: #222;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    cursor: pointer;
    width: 100%;
    font-size: 16px;
    transition: all 0.3s ease;
  } 
  .submit-btn:hover {
    background-color: #222;
    color: #FCBA03;
  }
 </style>