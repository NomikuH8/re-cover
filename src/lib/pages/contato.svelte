<div class="everything">
  <form>
    <span>Primeiro Nome*</span>
    <input required type="text" placeholder="ex: Henrique">

    <span>Último Nome*</span>
    <input required type="text" placeholder="ex: Maia Cardosa">

    <span>Seu email*</span>
    <input required type="email" placeholder="ex: email@mail.com">

    <span>Assunto</span>
    <input required type="text" placeholder="ex: Doação">

    <span>Informe sua dúvida*</span>
    <textarea required cols="50" rows="5"></textarea>

    <div>
      <button type="submit">Enviar</button>
    </div>
  </form>
  <div class="vertical-line"></div>
  <div class="infos">
    <h3>Contato</h3>
    <span>Endereço: Joinville, SC</span>
    <span>Vakinha: <a href="#">vakinha.com/vaquinha/ongrecover</a></span>
    <span>E-mail: <a href="mailto:recover@recover.com">recover@recover.com</a></span>
    <span>Telefone: (47) 99999-9999</span>
  </div>
</div>

<style lang="scss">
  .everything {
    padding: 0 3%;
    margin-bottom: 2%;
    display: flex;
    justify-content: center;
    gap: 78px;
  }

  form {
    display: flex;
    flex-direction: column;

    input, textarea {
      margin-bottom: 11px;
      padding: 0 8px;
      border: 2px solid #9b9b9b;
      font-size: 16px;
      line-height: 30px;
      resize: none;
      font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
    }

    button {
      border: 2px solid #e2e2e2;
      background-color: rgba(155, 155, 155, 0.72);
      padding: 12px 0;
      width: 150px;
      cursor: pointer;
    }
  }

  .infos {
    display: flex;
    flex-direction: column;
  }

  .vertical-line {
    border-left: 1px solid rgba(38, 39, 39, 0.32);
  }
</style>