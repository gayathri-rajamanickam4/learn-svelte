<script>
import ContactCard from './ContactCard.svelte';

	export let name;

	let randomNumber = Math.random();

	$: processedName  = name + " " + randomNumber;

	function toggleName() {
		if (name === 'world'){
			name = 'all'
		}
		else{
			name = 'world'
		}
			
	}

	function changeRandom(){
		randomNumber = Math.random();
	}
</script>

<main>
	<h1>Hello {processedName}!. Day 2 today</h1>
	<button on:click={toggleName}>Toggle Name</button>
	<button on:click={changeRandom}>Change Random</button>
	<input type="text" bind:value={name}/>

	</main>
	<ContactCard {name}/>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>