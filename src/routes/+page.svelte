<script lang="ts">
	let chars =
		'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()-_=+`~,.<>/\\;:\'"';

	async function randomise(e: Event) {
		let target = e.target as HTMLElement;
		let oldtext = target.dataset.oldtext;
		for (let i = 0; i < 25; i++) {
			await new Promise((r) => {
				setTimeout(r, 25);
			});
			target.innerText = chars[Math.floor(Math.random() * chars.length)];
		}
		target.innerText = oldtext || '!';
	}
</script>

<h1>
	{#each 'Crazy_Cat911' as letter}
		<span role="none" onmouseenter={randomise} data-oldtext={letter}>{letter}</span>
	{/each}
</h1>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Syne+Mono&display=swap');

	h1 {
		font-family: 'Syne Mono', monospace;
		font-size: 250px;
	}
</style>
