<script lang="ts">
  import { Router, link, Route } from 'svelte-navigator'
  import headerImage from './assets/header.png'

  import facebookIcon from './assets/facebook.svg'
  import twitterIcon from './assets/twitter.svg'
  import instagramIcon from './assets/instagram.svg'
  import youtubeIcon from './assets/youtube.svg'
  import Home from './lib/pages/home.svelte';
  import Ecossistema from './lib/pages/ecossistema.svelte';

  const socialMedia = [
    {
      name: 'facebook',
      link: 'https://facebook.com',
      icon: facebookIcon,
    },
    {
      name: 'twitter',
      link: 'https://twitter.com',
      icon: twitterIcon,
    },
    {
      name: 'youtube',
      link: 'https://youtube.com',
      icon: youtubeIcon,
    },
    {
      name: 'instagram',
      link: 'https://instagram.com',
      icon: instagramIcon,
    },
  ]
</script>

<Router>
  <header>
    <img src={headerImage} alt="header">
    <div>
      <nav>
        <ul>
          <li><a href="/" use:link>HOME</a></li>
          <li><a href="/ecossistema" use:link>ECOSSISTEMA</a></li>
          <li><a href="/como-ajudar" use:link>COMO AJUDAR?</a></li>
          <li><a href="/sobre" use:link>SOBRE NÓS</a></li>
          <li><a href="/contato" use:link>CONTATO</a></li>
        </ul>
      </nav>
      <ul class="redes-sociais">
        {#each socialMedia as i}
          <li>
            <a href={i.link} target="_blank" referrerpolicy="no-referrer">
              <img src={i.icon} alt={i.name}>
            </a>
          </li>
        {/each}
      </ul>
    </div>
  </header>
  <main>
    <Route path="/" component={Home} />
    <Route path="/ecossistema" component={Ecossistema} />
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
</style>
