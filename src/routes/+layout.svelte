<script lang="ts">
	import './styles.css';
	import iconNotification from "$lib/assets/notification.svg";
	import Navbar from "./Navbar.svelte";
	import {page} from "$app/stores";
</script>

<main class="page">
	{#if !$page.url.pathname.startsWith('/user')}
		<div class="header">
			<span class="location">Lviv, Ukraine</span>

			<img src={iconNotification} alt="" class="icon-notification">
		</div>
	{/if}

	<slot/>

	<Navbar/>
</main>

<style>
	.header {
		display: flex;
		flex-direction: row;
		align-items: center;
		padding: 20px;
		position: sticky;
		top: 0;
		background: var(--app-background);
	}

	.location {
		font-size: 14px;
		font-weight: 500;
		color: #121212;
	}

	.icon-notification {
		width: 24px;
		height: 24px;
		margin-left: auto;
	}
</style>


