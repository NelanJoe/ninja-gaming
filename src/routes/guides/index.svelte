<script context="module">
	export async function load({ fetch }) {
		const res = await fetch('https://jsonplaceholder.typicode.com/posts');
		const guides = await res.json();

		if (res.ok) {
			return {
				props: {
					guides
				}
			};
		}
		return {
			status: res.status,
			error: new Error('Cloud not fetch the guides')
		};
	}
</script>

<script>
	export let guides;
</script>

<div class="guides">
	<ul>
		{#each guides as guide}
			<li>
				<a sveltekit:prefetch href={`/guides/${guide.id}`}>{guide.title}</a>
			</li>
		{/each}
	</ul>
</div>

<style>
	.guides {
		display: flex;
		justify-content: center;
	}

	ul {
		list-style-type: none;
		padding: 0;
	}
	ul li a {
		margin: 10px auto;
	}
	a {
		display: inline-block;
		padding: 10px;
		border: 1px dotted rgba(225, 225, 225, 0.2);
	}
</style>
