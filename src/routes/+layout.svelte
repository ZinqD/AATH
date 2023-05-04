<script>
	import Header from '../lib/components/Header.svelte';
	import Footer from '../lib/components/Footer.svelte';
	import './styles.css';
 	import { fly } from 'svelte/transition'
  import { cubicIn, cubicOut } from 'svelte/easing'

  export let data

  const duration = 300
  const delay = duration + 100
  const y = 10

  const transitionIn = { easing: cubicOut, y, duration, delay }
  const transitionOut = { easing: cubicIn, y: -y, duration }
	</script>

<div class="app">
	<Header />

	<main>
  {#key data.pathname}
  <div
    in:fly={transitionIn}
    out:fly={transitionOut}
		>
    <slot />
  </div>
{/key}
</main>

	<Footer />
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 90rem;
		margin: 0 auto;
		box-sizing: border-box;
	}
	@media (min-width: 480px) {
	}
</style>