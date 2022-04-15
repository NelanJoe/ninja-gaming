<script>
	import Title from '$lib/title.svelte';
	import '../styles/global.css';
</script>

<header>
	<nav>
		<Title title="Ninja Gaming Guides" />
		<div class="links">
			<a href="/">Home</a>
			<a href="/about">About</a>
			<a href="/guides">Guides</a>
		</div>
	</nav>
</header>
<main>
	<!-- Page Content -->
	<slot />
</main>
<footer>
	<p>Copyright &copy; Gaming Guides</p>
</footer>

<style>
	header {
		text-align: center;
        background: rgba(0, 0, 0, .1);
	}
	main {
		min-width: 960px;
		margin: 20px auto;
	}
	footer {
		text-align: center;
	}

    nav {
        margin: auto 3rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 1rem;
    }
</style>
