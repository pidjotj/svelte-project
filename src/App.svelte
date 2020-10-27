<script>
	let firstName = "Jerem";
	let lastName = "Pidjot";
	let beltColor = "White";

	// $: is the way to declare a "reactive value" it will be update when the value change.
	// It can be use on a console log as the example below -> a log will be trigger every time 'beltColor' change
	$: fullName = `${firstName} ${lastName}`;
	$: console.log(beltColor);
	// a reactive value can take multiple statements
	$: {
		console.log(fullName);
		console.log(beltColor);
	}

	const handleClick = () => {
		beltColor = 'blue';
	};

	// Tip : Useless because of the bind:value
	// const handleInput = event => {
	// 	beltColor = event.target.value;
	// }
</script>

<main>
	<h1>Hello {fullName}!</h1>
	<p style="color: {beltColor}">{beltColor} belt</p>
	<!--<input type="text" on:input={handleInput} value={beltColor}>-->
	<!-- bind:value -> on:input= & value= at the same time {strong} -->

	<input type="text" bind:value={firstName} >
	<input type="text" bind:value={lastName} >
	<input type="text" bind:value={beltColor} >
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>