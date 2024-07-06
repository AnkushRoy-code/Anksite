<script>
	let name = '';
	let email = '';
	let message = '';
	let successMessage = '';
	let errorMessage = '';

	async function handleSubmit() {
		if (name && email && message) {
			const response = await fetch('https://formspree.io/f/xgvwepnd', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				},
				body: JSON.stringify({
					name,
					email,
					message
				})
			});

			if (response.ok) {
				successMessage = 'Thank you for your message!';
				errorMessage = '';
				name = '';
				email = '';
				message = '';
			} else {
				successMessage = '';
				errorMessage = 'Make sure you have you have given your correct email.';
			}
		} else {
			successMessage = '';
			errorMessage = 'Please fill out all fields.';
		}
	}
</script>

<main>
	<div class="contact-form">
		<h2>Contact Me</h2>

		<div class="form-field">
			<label for="name">Name:</label>
			<input type="text" id="name" placeholder="eg: Michael Madhusudan Datta" bind:value={name} />
		</div>

		<div class="form-field">
			<label for="email">Email:</label>
			<input type="email" id="email" placeholder="eg: fun@email.com" bind:value={email} />
		</div>

		<div class="form-field">
			<label for="message">Message:</label>
			<textarea
				id="message"
				placeholder="Your response to my website or any suggestions, or anything you might want to know that I can help with."
				bind:value={message}
			></textarea>
		</div>

		<div class="form-field">
			<button on:click={handleSubmit}>Send</button>
		</div>

		{#if successMessage}
			<div class="message success">{successMessage}</div>
		{/if}

		{#if errorMessage}
			<div class="message error">{errorMessage}</div>
		{/if}
	</div>
</main>

<style>
	main {
		padding: 4rem 5rem 0;
		background-color: var(--mocha-surface0);
		color: var(--mocha-text);
		min-height: 100vh;
	}

	.contact-form {
		display: flex;
		flex-direction: column;
		min-width: 70vw;
		max-width: 90vw;
		min-height: 70vh;
		max-height: 90vh;
		margin: auto;
		padding: 4rem;
		border: 1px solid var(--mocha-overlay1);
		border-radius: 10px;
		background-color: var(--mocha-base);
	}

	.form-field {
		margin-bottom: 15px;
	}

	.form-field label {
		display: block;
		margin-bottom: 5px;
		font-weight: bold;
		color: var(--mocha-text);
	}

	.form-field input,
	.form-field textarea {
		width: 100%;
		padding: 10px;
		box-sizing: border-box;
		border: 1px solid var(--mocha-overlay0);
		border-radius: 5px;
		font-size: 16px;
		background-color: var(--mocha-surface0);
		color: var(--mocha-text);
	}

	.form-field input::placeholder,
	.form-field textarea::placeholder {
		color: var(--mocha-subtext0);
	}

	.form-field input:focus,
	.form-field textarea:focus {
		border-color: var(--mocha-blue);
		outline: none;
		background-color: var(--mocha-surface1);
	}

	.form-field button {
		padding: 10px 20px;
		background-color: var(--mocha-blue);
		color: var(--mocha-crust);
		border: none;
		border-radius: 5px;
		cursor: pointer;
		font-size: 16px;
	}

	.form-field button:hover {
		background-color: var(--mocha-sapphire);
	}
	.form-field input:-webkit-autofill,
	.form-field input:-webkit-autofill:hover,
	.form-field input:-webkit-autofill:focus,
	.form-field textarea:-webkit-autofill,
	.form-field textarea:-webkit-autofill:hover,
	.form-field textarea:-webkit-autofill:focus {
		border: 1px solid var(--mocha-blue);
		-webkit-text-fill-color: var(--mocha-text);
		-webkit-box-shadow: 0 0 0px 1000px var(--mocha-surface1) inset;
		transition: background-color 5000s ease-in-out 0s;
	}
	.message {
		margin-top: 10px;
		font-weight: bold;
	}

	.success {
		color: var(--mocha-green);
	}

	.error {
		color: var(--mocha-red);
	}
</style>
