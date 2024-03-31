<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition'

	let src = 'images/lilypad.png';
	let ready = false;
	onMount(() => {
		ready = true
	})
</script>

<div transition:fade>
	<button type="button" class="btn btn__primary">Sign up</button>
	<button type="button" class="btn btn__primary">Login</button>
</div>
	
{#if ready}
	<h1 transition:fade> Welcome to Froggy Chat</h1>
	<img transition:fade src={src} alt="lilypad"/>
{/if}

<style>
	img {
		display: flex;
		justify-content: center;
		margin-left: auto;
		margin-right: auto;
		margin-top: 5%;
		width: 30%;
		transition: transform 2s ease-in-out;
	}

	img:hover {
		transform: rotate(360deg);
	}

	h1 {
		display: flex;
		justify-content: center;
		color: black;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}

	div {
		display: flex;
		justify-content: flex-end;
		gap: 4px;
		margin-top: 30px;
		margin-right: 30px;
	}

	button {
      padding: 0.6em 1em;
      font-weight: 600;
      color: black;
      background-color: transparent;
      border: 1px solid blue;
      border-radius: 4px;
          cursor: pointer;
	}

	button:hover {
      color: black;
      border-color: transparent;
      background-color: cornflowerblue;
    }

	button:active {
      background-color: cornsilk;
    }
</style>