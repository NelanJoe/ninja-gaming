<script>
    export let title = 'Ninja Gaming';
</script>

<div class="title">
	<img src="/gaming-stick.svg" alt="ninja" />
	<h1>{title}</h1>
</div>

<style>
	.title {
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.title img {
		display: inline-block;
        width: 40px;
        height: 40px;
	}

    .title h1 {
        margin-left: 10px;
    }
</style>
