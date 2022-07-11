<script context="module">
	/** @type {import('@sveltejs/kit').Load} */
	export function load({ error, status }) {
		return {
			props: {
				title: `${status}: ${error.message}`,
				error_status: `${status}`,
				error_message: `${error.message}`
			}
		};
	}
</script>

<script>
	export let title, error_status, error_message;
</script>

<svelte:head>
	<title>{title}</title>
</svelte:head>

<div class="flex h-screen">
	<div class="m-auto text-center">
		<h1 class="text-5xl">Error {error_status}</h1>
		<span class="text-lg">{error_message}</span>
	</div>
</div>
