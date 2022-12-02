<script>
	import { Configuration, OpenAIApi } from "openai";
	let value = ""
	let output = ""
	async function handleSubmit () {
		const configuration = new Configuration({
			organization: "org-Jc3sxfzl7ZxYjl2pggiPd2bE",
			apiKey: import.meta.env.VITE_OPENAI_API_KEY,
		});
		const openai = new OpenAIApi(configuration);
		const response = await openai.createCompletion({
			model: "text-davinci-003",
			prompt: `Correct this to standard English: ${value}`,
			temperature: 0,
			max_tokens: 100,
		})
		console.log('response', response)
		output = response.data.choices[0].text?.slice(2)
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
		background-color: darkgray;
		width: 33vw; 
		height: 70vh;
	}
	.btn {
		display: flex;
		align-items: center;		
	}

	button {
		background-color: black;
		color: white;
	}


@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
