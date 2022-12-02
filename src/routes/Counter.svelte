<script>
	let value = ""
	let output = ""
	function handleSubmit () {
		output = value
	}
</script>

<div class="grammar">
	<div>
		<h3>Input</h3>
		<textarea bind:value></textarea>
	</div>
	<div class="btn">
		<button on:click={handleSubmit}>send</button>
	</div>
	<div>
		<h3>Output</h3>
		<textarea readonly>{output}</textarea>
	</div>
</div>

<style>
	.grammar {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: space-around;
		gap: 5vw;
	}
	textarea {
		width: 33vw; 
		height: 70vh;
	}
	.btn {
		display: flex;
		align-items: center;		
	}

	button {
		background-color: black;
	}


@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
