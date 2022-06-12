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
	import { Button } from '@opentj/jui';
</script>

<svelte:head>
	<title>Buttons</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="mt-4">
	<Button class="btn">Button</Button>
	<Button class="btn btn-primary">Primary</Button>
	<Button class="btn btn-secondary">Secondary</Button>
	<Button class="btn btn-accent">Accent</Button>
	<Button class="btn btn-ghost">Ghost</Button>
	<button class="btn btn-link">Link</button>
</div>

<div class="mt-4">
	<Button class="btn btn-info">Info</Button>
	<Button class="btn btn-success">Success</Button>
	<Button class="btn btn-warning">Warning</Button>
	<Button class="btn btn-error">Error</Button>
</div>

<div class="mt-4">
	<Button class="btn btn-outline btn-info">Info</Button>
	<Button class="btn btn-outline btn-success">Success</Button>
	<Button class="btn btn-outline btn-warning">Warning</Button>
	<Button class="btn btn-outline btn-error">Error</Button>
</div>

<div class="mt-4">
	<Button class="btn gap-2">
		<svg
			xmlns="http://www.w3.org/2000/svg"
			class="h-6 w-6"
			fill="none"
			viewBox="0 0 24 24"
			stroke="currentColor"
			><path
				stroke-linecap="round"
				stroke-linejoin="round"
				stroke-width="2"
				d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"
			/></svg
		>
		Button
	</Button>
</div>

<div class="mt-4">
	<button><a href="https://daisyui.com/components/button/">更多用法 ...</a></button>
</div>
