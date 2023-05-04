<script>
  import heroImg from "$lib/images/about-hero.webp";
  
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
          <h2 class="IndexPageTitle">About Me</h2>
					<p class="IndexText">Hello I'm Samantha, a passionate advocate for modern country neutral decor, calm spaces and interiors affordable for any budget and style of home.</p>
					<p class="IndexText">As a little girl I'd frequently be changing my bedroom around and 'shopping my home' in the hope to give it a new look. Now having my own home has allowed me to experiment with styles and taste, but it wasn't until 2019 during lock down when my decor began impacting my health. I was having frequent migraines being stuck inside a very noisy and bright decor home environment, therefore set about calming the home to a more neutral palette.</p>
					<p class="IndexText">In 2020, When we were thinking of putting the house on the market, I had kept an eye on properties which were not selling or even receiving enough interest. So, I've founded All About The Home, a home staging and interior design business to help those trying to sell or refresh their home.</p>
					<p class="IndexText">As a busy Mum to three children, I know life has a habit of getting in the way, so when it comes to selling a house its an added burden you don't really need. So that's where All About The Home can help. Let me provide you with some tips and tricks or even a full hands on home staging service to transform your home from cluttered ,to calm and inviting in addition to receiving the value you should for your home. If its a room refresh I can also work with you to help bring your vision to life on your budget too.</p>
					<h2 class="IndexPageTitle">Trust The Process</h2>
					<p class="IndexText">I understand that being told the home you love isn't up to market standards can be hard to hear, so I'll ensure the process runs as smoothly as possible to avoid any un necessary stress or upset. Its important to remember the second you decide to sell your house it's no longer your home and one that now needs to appeal to buyers. Keep in mind that the process of home staging will lead to profit made and the journey to your next home.</p>
          <button on:click={redirectToContact}>LEARN MORE</button>
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
    order: 2;
    flex: 1;
    margin-right: 1rem;
  }


  .image img {
    max-width: 100%;
  }

  @media screen and (min-width: 768px) {
    .image {
      flex: 0 0 30%;
      margin-right: 2rem;
    }
  }


  .text {
    order: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    flex: 1;
  }

  .IndexPageTitle {
    font-size: calc(0.5rem + 1vw);
    font-weight: bold;
    margin-bottom: 1.5rem;
		text-transform:uppercase;
  }

  .IndexText {
    font-size: 0.9rem;
    margin-bottom: 1.5rem;
		text-align: left;
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
