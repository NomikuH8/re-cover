<script lang="ts">
  import { Router, link, Route } from "svelte-navigator";
  import headerImage from "./assets/header.png";

  import instagramIcon from "./assets/instagram.svg";
  import facebookIcon from "./assets/facebook.svg";
  import twitterIcon from "./assets/twitter.svg";
  import youtubeIcon from "./assets/youtube.svg";

  import Ecossistema from "./lib/pages/ecossistema.svelte";
  import ComoAjudar from "./lib/pages/comoAjudar.svelte";
  import Contato from "./lib/pages/contato.svelte";
  import Sobre from "./lib/pages/sobre.svelte";
  import Home from "./lib/pages/home.svelte";
  import CanaisDenuncia from "./lib/pages/canaisDenuncia.svelte";

  const navLinks = [
    {
      name: "HOME",
      link: "/",
    },
    {
      name: "ECOSSISTEMA",
      link: "/ecossistema",
    },
    {
      name: "COMO AJUDAR?",
      link: "/como-ajudar",
    },
    {
      name: "CANAIS DE DENÚNCIA",
      link: "/canais-de-denuncia",
    },
    {
      name: "SOBRE NÓS",
      link: "/sobre",
    },
    {
      name: "CONTATO",
      link: "/contato",
    },
  ];

  const socialMedia = [
    {
      name: "facebook",
      link: "https://facebook.com",
      icon: facebookIcon,
    },
    {
      name: "twitter",
      link: "https://twitter.com",
      icon: twitterIcon,
    },
    {
      name: "youtube",
      link: "https://youtube.com",
      icon: youtubeIcon,
    },
    {
      name: "instagram",
      link: "https://instagram.com",
      icon: instagramIcon,
    },
  ];

  let currPage = "/";
</script>

<Router>
  <header>
    <img src={headerImage} alt="header" />
    <div>
      <nav>
        <ul>
          {#each navLinks as nav}
            <li>
              <a
                href={nav.link}
                class={currPage === nav.link ? "selected" : ""}
                on:click={() => (currPage = nav.link)}
                use:link>{nav.name}</a
              >
            </li>
          {/each}
        </ul>
      </nav>
      <ul class="redes-sociais">
        {#each socialMedia as i}
          <li>
            <a href={i.link} target="_blank" referrerpolicy="no-referrer">
              <img src={i.icon} alt={i.name} />
            </a>
          </li>
        {/each}
      </ul>
    </div>
  </header>
  <main>
    <Route path="/" component={Home} />
    <Route path="/ecossistema" component={Ecossistema} />
    <Route path="/como-ajudar" component={ComoAjudar} />
    <Route path="/canais-de-denuncia" component={CanaisDenuncia} />
    <Route path="/sobre" component={Sobre} />
    <Route path="/contato" component={Contato} />
  </main>
  <footer>
    <span class="logo-text">re:cover</span>
    <span>Ajude a salvar uma vida animal, apoie esta causa!</span>
  </footer>
</Router>

<style lang="scss">
  header {
    img {
      width: 100%;
    }

    div {
      display: flex;
      justify-content: space-between;
    }

    div > nav > ul {
      display: flex;
      gap: 24px;
      list-style-type: none;

      .selected {
        color: green;
      }

      a {
        text-decoration: none;
        color: #262627;
      }
    }
  }

  .redes-sociais {
    list-style-type: none;
    display: flex;
    gap: 21px;
    margin-right: 40px;
  }

  footer {
    height: 210px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #acfe89;
    padding: 0 5%;

    .logo-text {
      font-size: 48px;
      color: #a4854d;
    }

    span {
      max-width: 320px;
      text-align: center;
    }
  }

  @media only screen and (max-width: 768px) {
    nav > ul {
      flex-wrap: wrap;
    }
  }
</style>
