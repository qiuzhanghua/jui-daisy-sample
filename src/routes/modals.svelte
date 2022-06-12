<script context="module">
	import { browser, dev } from '$app/env';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<script>
	import { Button, Modal } from '@opentj/jui';
	let showModal = false;
</script>

<svelte:head>
	<title>Modals</title>
	<meta name="description" content="About Modals" />
</svelte:head>

<div class="mt-4">
	<Button class="btn btn-active" on:click={() => (showModal = !showModal)}>Open Modal</Button>
</div>

<Modal
	id="modal"
	{showModal}
	modalClass="fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 shadow-xl z-50 overflow-auto bg-white rounded-lg"
	backdropClass="fixed top-0 left-0 h-screen w-screen z-[10] bg-gray-200 opacity-75"
>
	<div class="flex flex-col">
		<div class="p-1 flex justify-center">Header</div>
		<div class="p-1">This is a Dialog</div>
		<div><Button class="btn btn-secondary" on:click={() => (showModal = false)}>Close</Button></div>
	</div>
</Modal>
