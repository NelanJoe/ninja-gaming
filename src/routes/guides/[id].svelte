<script context="module">
	export async function load ({fetch, params}) {
        await new Promise(resolve => setInterval(resolve, 1000))
        const id = params.id;
        const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
        const guide = await res.json();


        if(res.ok) {
            return {
                props: {
                    guide
                }
            }
        }
        return {
            stasus: res.status,
            error: new Error("Tidak dapat di load")
            // redirect: 'guides/'
        }
    } 
</script>

<script>
    export let guide;
</script>

<div class="guide">
	<h2>{guide.title}</h2>
	<p>{guide.body}</p>
</div>

<style>
	.guide {
		margin: 10px 36px;
		padding: 10px;
		border: 1px dotted rgba(225, 225, 225, 0.2);
	}
</style>
