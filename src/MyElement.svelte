<svelte:options tag="my-element" />

<script>
	export let string = "";
	export let num = 0;
	export let array = [];
	export let bool = undefined;
	export let handler = () => { alert('hello!'); };
</script>

<div>
	<h1>This is a custom element compiled by Svelte!</h1>
	<ul>
		<li>String: {string}</li>
		<li>Number: {num}</li>
		<li>Array: {array.join(',')}</li>
		<li>Boolean: {bool !== undefined}</li>
	</ul>
	<button disabled={bool !== undefined} on:click={handler}>Click me</button>
	<details open>
		<slot>You can put something in the component's slot and it will show up here!</slot>
	</details>
</div>

<style>
	:host {
		display: block;
	}

	div {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		border: 2px solid red;
		border-radius: 3px;
	}

	@media (min-width: 640px) {
		div {
			max-width: none;
		}
	}
</style>