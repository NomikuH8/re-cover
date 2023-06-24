<script lang="ts">
  import logoImage from "../../assets/logo.png";
</script>

<div class="everything">
  <img src={logoImage} alt="logo" />
  <div>
    <p>
      A ONG de <strong>RE:COVER</strong> foi fundada em 2023 com o objetivo de proteger
      e preservar a vida animal. Somos uma organização sem fins lucrativos que busca
      conscientizar a sociedade sobre a importância da preservação da fauna brasileira,
      promovendo ações e projetos que contribuam para a manutenção dos ecossistemas
      naturais.
    </p>

    <p>
      <strong>FUNDADORES:</strong>
      Graziela Torres, Henrique Maia, João Menna, Ricardo Gabriel e Sophia Eggert.
    </p>
  </div>
</div>

<style lang="scss">
  .everything {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 500px;
    gap: 96px;
    font-size: 20px;
    padding: 0 5%;

    img {
      width: 300px;
    }
  }

  @media only screen and (max-width: 768px) {
    .everything {
      flex-wrap: wrap;
      height: 800px;
    }
  }
</style>