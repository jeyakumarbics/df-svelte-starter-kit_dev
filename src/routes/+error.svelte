<script>
	import { page } from '$app/stores';
	import { Alert, Button } from 'flowbite-svelte';
	import { InfoCircleSolid } from 'flowbite-svelte-icons';
	import '$lib/css/style.scss';
	import '../app.postcss';
</script>

{#if $page?.error}
	<Alert color="red" class="mt-5 w-[60rem] m-auto mb-10">
		<div class="flex items-center gap-3">
			<InfoCircleSolid slot="icon" class="w-5 h-5" />
			<span class="text-lg font-medium"
				>Oops! It seems there has been an error, sorry about that :(</span
			>
		</div>
		<p class="mt-2 mb-4 text-sm">
			{#if $page?.error?.message}
				<p>{$page?.error?.message}</p>
			{/if}
		</p>
		<div class="flex gap-2">
			<!-- <Button size="xs"><Eye class="w-4 h-4 mr-2" />View more</Button> -->
			<Button size="xs" href="/" outline class="dark:!text-primary-800">Go to Home</Button>
		</div>
	</Alert>
{/if}
