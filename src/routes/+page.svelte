<script>
  import heroImg from "$lib/images/home-hero.webp";
  
  function redirectToContact() {
    window.location.href = '/contact';
  }
</script>

<section class="homepage-section">
  <div class="container">
    <div class="content">
      <div class="row">
        <div class="column image">
          <img src="{heroImg}" alt="All About the Home">
        </div>
        <div class="column text">
          <h1 class="IndexPageTitle">WELCOME</h1>
          <p class="IndexText">AFFORDABLE HOME STAGING AND INTERIOR STYLING TO TRANSFORM YOUR HOME</p>
          <button on:click={redirectToContact}>GET IN TOUCH</button>
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  :root {
    --header-height: 80px;
    --footer-height: 60px;
  }

  .homepage-section {
    height: calc(80vh - var(--header-height) - var(--footer-height));
    margin-top: var(--header-height);
    margin-bottom: var(--footer-height);
  }

  .container {
    max-width: 80vw;
    margin: 0 auto;
  }

  .content {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    padding: 3rem;
    background-color: #898d7c;
    height: 100%;
    width: 100%;
  }

  .row {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }

  .column {
    flex: 1;
    margin: 1rem;
  }

   .image {
    order: 1;
    flex: 1;
    margin-right: 1rem;
  }


  .image img {
    max-width: 100%;
  }

  @media screen and (min-width: 768px) {
    .image {
      flex: 0 0 50%;
      margin-right: 2rem;
    }
  }


  .text {
    order: 2;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    flex: 1;
  }

  .IndexPageTitle {
    font-size: calc(2rem + 1vw);
    font-weight: bold;
    margin-bottom: 1.5rem;
  }

  .IndexText {
    font-size: calc(1rem + 0.5vw);
    margin-bottom: 1.5rem;
  }

  button {
    font-size: 1.2rem;
    background-color: #b1b0a4;
    color: #605e56;
    padding: 1rem 2rem;
    border: none;
    font-weight: lighter;
    font-family: 'Lora', serif;
    border-radius: 15px;
    transition: all 0.3s ease;
  }

  button:hover {
    background-color: #605e56;
    color: #fff;
    cursor: pointer;
  }
</style>
