<script>
  const menu = [
    { name: "Home", url: "/" },
    { name: "About Me", url: "/about-me" },
    { name: "Home Staging & Interior Styling", url: "/home-staging" },
    { name: "Services and Prices", url: "/services" },
    { name: "Gallery", url: "/gallery" },
    { name: "Contact Me", url: "/contact" },
  ];
</script>

<style>
@media (max-width: 768px) {
  .hamburger {
    display: block;
  }
  nav ul {
    display: none;
  }
}
  .header {
    background-color: #898d7c;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2rem 10rem;
  }

  .logo {
    font-size: 1.5rem;
    font-weight: bold;
  }

  .nav {
    display: flex;
    justify-content: center;
    align-items: center;
    
  }

  .nav a {
    color: #000;
    text-decoration: none;
    padding: 0.5rem;
    margin: 0 0.5rem;
    transition: all 0.3s ease;
  }

  .nav a:hover {
    color: #fff;
    background-color: #605e56;
    border-radius: 0.25rem;
  }
</style>
<div class="header">
  <div class="logo"><a href="/">ALL ABOUT THE HOME</a></div>
  <nav class="nav">
    {#each menu as item}
      <a href="{item.url}">{item.name}</a>
    {/each}
  </nav>
</div>


