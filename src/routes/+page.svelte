<link rel='stylesheet' href='//cdn.jsdelivr.net/npm/hack-font@3.3.0/build/web/hack-subset.css'>

<svelte:head>
	<title>QR Games Studio</title>
</svelte:head>

<style>
	h1 {
		font-size: 2em;
	}
	h2 {
		font-size: 1.5em;
	}
	p {
		font-size: 1.2em;
	}
	ul {
		font-size: 1.2em;
		padding-left: 3ex;
	}
	li {
		list-style-type: '- ';
	}
	:root {
			display: flex;
			flex-direction: column;
			align-items: center;
			background: #000;
			color: #0f0;
			font-family: "Hack", monospace;
			margin: 8px 16px;

			& > * {
				margin-left: 0;
				padding-left: 0;
			}
	}
</style>

<script>
	/** @type {Array<import('$lib').TeamMember>} */
	const people = [{
		github: 'StastnyJ'
	}, {
		github: 'esoadamo',
		web: "https://adamhlavacek.com"
	}];

	import manifest from '$lib/manifest.json';
	const games = Object.values(manifest);
</script>

<h1>QR Games Studio</h1>

<p>Creating open-source games that fit into a single QR code</p>

<h2>Team</h2>
<ul>
	{#each people as person}
		<li><a href="https://github.com/{person.github}">{person.github}</a>
			{#if person.web}
				<a href="{person.web}">[web]</a>
			{/if}
		</li>
	{/each}
</ul>

<h2>Games</h2>
<ul>
	{#each games as game}
		<li>
			{game.name} (v{game.version}) <a href="{game.url}">[play]</a>
		</li>
	{/each}
</ul>