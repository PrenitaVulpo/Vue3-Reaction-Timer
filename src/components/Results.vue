<template>
	<div class="results">
		Reaction time: {{ score }} ms
	</div>
</template>

<script>
export default {
	props: ['score'],
}
</script>

<style>
    .results {
        width: 400px;
        border-radius: 20px;
        background: #0faf87;
        color: #fff;
        text-align: center;
        padding: 100px 0;
        margin: 40px auto;
    }
</style>
