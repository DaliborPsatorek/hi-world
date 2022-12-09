<template>
	<div>
		<div class="title">Counter App</div>
		<div class="counter-continer">
			<div class="box" v-on:click="minus()">-</div>
			<div class="box" v-if="counter != 0">{{ counter }}</div>
			<div class="box" v-else>Zero</div>
			<div class="box" v-on:click="plus()">+</div>
		</div>
	</div>
</template>

<script setup>
	console.clear()
	let counter = ref(0)
	const plus = () => {
		counter.value += 1
	}
	const minus = () => {
		counter.value -= 1
	}
</script>

<style>
	.title {
		font-size: 5rem;
		margin-bottom: 2rem;
	}
	body {
		background-color: rgb(14, 239, 255);
		display: flex;
		justify-content: center;
	}
	.counter-continer {
		display: flex;
		justify-content: space-between;
	}
	.box {
		background-color: rgb(0, 89, 255);
		font-size: xx-large;
		color: rgb(206, 205, 205);
		height: 3rem;
		padding-left: 1rem;
		padding-right: 1rem;
		width: auto;
		text-align: center;
	}
</style>
