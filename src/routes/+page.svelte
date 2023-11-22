<script lang="ts">
	import Card from "$lib/common/Card.svelte";
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Home" />
</svelte:head>

<div class="block">
	<h1>Available blood checks</h1>
	<p>
		You have the option to choose a blood check to be performed on your donated blood at <b>no additional cost</b>
	</p>
</div>

<div class="grid">
	<Card name="Vitamin B12" icon="pill" />
	<Card name="Vitamin D3" icon="pill" />
	<Card name="Complete Blood Count (CBC)" icon="microscope"/>
	<Card name="Blood Type and Rh Factor" icon="microscope"/>
	<Card name="Blood Glucose Levels" icon="microscope"/>
</div>


<style>
	.block {
		display: flex;
		flex-direction: column;
		gap: 16px;
		margin: 32px 20px 0 20px;
	}

	p {
		color: #A8ACB8;
	}

	b {
		color: #121212;
	}

	.grid {
		padding: 20px;
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 12px
	}
</style>
