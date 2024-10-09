<script>
	export let data;
	import '../styles/global.css';
</script>

<section>
	{#if data && data.items}
		<ul>
			{#each data.items as item}
				<li>
					<h2>{item.package_name}</h2>
					<img src="../freakbob-calling.webp" alt="freakbob" />
					<p>{item.description}</p>
				</li>
			{/each}
		</ul>
	{/if}
</section>

<style>
	ul {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		gap: 1em;
		padding: 0;
	}

	li {
		width: 17.5em;
		list-style-type: none;
		display: flex;
		flex-direction: column;
		align-items: center;
		background-color: var(--D-primary-mid-grey);
		border-radius: 5%;

		& h2 {
			font-weight: bold;
			font-size: 1.25em;
			padding: 1em;
			text-align: center;
		}

		& img {
			width: 12.5em;
			height: 12.5em;
			object-fit: cover;
			border-radius: 5%;
		}

		& p {
			width: 15em;
			padding: 1em 0;
		}
	}

	@keyframes pageLoadAnimation {
		0% {
			transform: translateX(-50%);
			opacity: 0;
		}

		100% {
			transform: translateX(0);
			opacity: 100%;
		}
	}

	section {
		animation: 0.8s cubic-bezier(0.34, -0.04, 0.17, 0.98) pageLoadAnimation;
	}
</style>
