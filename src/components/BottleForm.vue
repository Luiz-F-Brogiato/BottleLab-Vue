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
              <select name="BottleBody" id="BottleBody">
                <option value="">Selecione a estrutura da sua garrafa de preferência</option>
                <option value="">Garrafa Squeeze Cilíndrica</option>
              </select>
            </div>
               <div class="input-container">
              <label for="BottleNameTag">Escolha a sua frase(Max: 16 caracteres)</label>
              <input type="text" placeholder="Sua frase aqui" maxlength="16">
            </div>
             <div class="input-container">
              <label for="BottleNameTagSize">Escolha o tamanho do texto</label>
              <select name="BottleNameTagSize" id="BottleNameTagSize">
                <option value="">Selecione o tamanho da fonte</option>
                <option value="">Pequena</option>
                <option value="">Média</option>
                <option value="">Grande</option>
              </select>
            </div>
             <div class="input-container">
              <label for="BottleNameTagType">Escolha a tipografia do texto</label>
                <select name="BottleNameTagType" id="BottleNameTagType">
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
              <Label id="OptionalTittle" for="Optional">Selecione a cor da garrafa</label>
                <div class="checkbox-container">
                  <input type="checkbox" name="opcionais" v-model="opcionais" value="rosa">
                  <span>Rosa</span>
                  <input type="checkbox" name="opcionais" v-model="opcionais" value="preta" checked>
                  <span>Preta</span>
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