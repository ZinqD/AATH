<style>
  html, body {
    margin: 0;
    padding: 0;
    overflow-x: hidden;
  }

  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: #605e56;
    color: #fff;
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 999;
  }

  .logo {
    font-size: 2rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 2px;
  }

  .menu {
    display: flex;
    align-items: center;
  }

  .menu a {
    color: #fff;
    text-decoration: none;
    margin-left: 1.5rem;
    font-size: 1.2rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: all 0.3s ease;
  }

  .menu a:hover {
    color: #f2f2f2;
  }

  .hamburger {
    display: none;
    cursor: pointer;
    margin-right: 1rem;
  }

  .hamburger span {
    height: 3px;
    width: 25px;
    background-color: #fff;
    display: block;
    margin-bottom: 6px;
    position: relative;
    border-radius: 3px;
    z-index: 1;
  }

  .hamburger span:first-child {
    transform-origin: 0% 0%;
  }

  .hamburger span:nth-last-child(2) {
    transform-origin: 0% 100%;
  }

  .hamburger.active span:first-child {
    transform: rotate(45deg) translate(5px, 5px);
  }

  .hamburger.active span:nth-last-child(2) {
    transform: rotate(-45deg) translate(5px, -5px);
  }

  .hamburger.active span:nth-child(3) {
    opacity: 0;
  }

  @media screen and (max-width: 768px) {
    .menu {
      display: none;
    }

    .hamburger {
      display: block;
    }

    header.active {
      height: 100vh;
      position: fixed;
      top: 0;
      left: 0;
      z-index: 999;
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      background-color: #605e56;
      transition: all 0.5s ease;
    }

    header.active .menu {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-top: 2rem;
    }

    header.active .menu a {
      margin: 1rem 0;
      font-size: 2rem;
      text-transform: uppercase;
      letter-spacing: 2px;
    }
  }
</style>

<script>
  import { onMount } from 'svelte';
  import { goto } from '$app/navigation';
  import logo from '$lib/images/logo.svg';

  let headerHeight = 0;
  let showMenu = false;

  // Wait for the DOM to load before calculating header height
  onMount(() => {
    headerHeight = document.querySelector('header').offsetHeight;
  });

  function toggleMenu() {
    showMenu = !showMenu;
  }

  function navigateTo(path) {
    toggleMenu();
    goto(path);
  }
    const menu = [
    { name: "Home", url: "/" },
    { name: "About Me", url: "/about-me" },
    { name: "Home Staging & Interior Styling", url: "/home-staging" },
    { name: "Services and Prices", url: "/services" },
    { name: "Gallery", url: "/gallery" },
    { name: "Contact Me", url: "/contact" },
  ];
</script>

<header style="height: {headerHeight}px;">
  <div class="container">
    <div class="logo">
      <a href="/">
        <img src="{logo}" alt="All About the Home">
      </a>
    </div>
    <nav>
      <ul class="{showMenu ? 'show' : ''}">
        <li><a href="/" on:click|preventDefault={() => navigateTo('/')}>Home</a></li>
        <li><a href="/about" on:click|preventDefault={() => navigateTo('/about')}>About</a></li>
        <li><a href="/services" on:click|preventDefault={() => navigateTo('/services')}>Services</a></li>
        <li><a href="/gallery" on:click|preventDefault={() => navigateTo('/gallery')}>Gallery</a></li>
        <li><a href="/contact" on:click|preventDefault={() => navigateTo('/contact')}>Contact</a></li>
      </ul>
      <div class="hamburger" on:click={toggleMenu}>
        <span></span>
        <span></span>
        <span></span>
      </div>
    </nav>
  </div>
</header>
