<script>
	let email = '';
	let password = '';
</script>

<svelte:head>
	<title>Login | Library Management System</title>
</svelte:head>

<div class="login-page">
	<div class="login-card">
		<h1>Library Management</h1>
		<h2>Login</h2>

		<form>
			<div class="form-group">
				<label for="email">Email</label>
				<input
					id="email"
					type="email"
					bind:value={email}
					placeholder="Enter your email"
				/>
			</div>

			<div class="form-group">
				<label for="password">Password</label>
				<input
					id="password"
					type="password"
					bind:value={password}
					placeholder="Enter your password"
				/>
			</div>

			<button type="submit">Login</button>
		</form>

		<a href="/" class="forgot-password">Forgot password?</a>

		<p class="register-text">
			Don't have an account?
			<a href="/">Register</a>
		</p>
	</div>
</div>

<style>
	.login-page {
		min-height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #f5f5f5;
		padding: 20px;
	}

	.login-card {
		width: 100%;
		max-width: 420px;
		background-color: white;
		padding: 40px;
		border-radius: 12px;
		box-shadow: 0 8px 25px rgba(0, 0, 0, 0.12);
	}

	h1 {
		text-align: center;
		margin-bottom: 10px;
		font-size: 28px;
	}

	h2 {
		text-align: center;
		margin-bottom: 30px;
		font-size: 24px;
	}

	.form-group {
		margin-bottom: 20px;
	}

	label {
		display: block;
		margin-bottom: 8px;
		font-weight: 600;
	}

	input {
		width: 100%;
		box-sizing: border-box;
		padding: 12px;
		border: 1px solid #ccc;
		border-radius: 6px;
		font-size: 15px;
	}

	input:focus {
		outline: none;
		border-color: #555;
	}

	button {
		width: 100%;
		padding: 12px;
		border: none;
		border-radius: 6px;
		background-color: #333;
		color: white;
		font-size: 16px;
		cursor: pointer;
		margin-top: 5px;
	}

	button:hover {
		background-color: #222;
	}

	.forgot-password {
		display: block;
		text-align: center;
		margin-top: 20px;
		text-decoration: none;
	}

	.register-text {
		text-align: center;
		margin-top: 20px;
	}

	a {
		color: #333;
	}

	a:hover {
		text-decoration: underline;
	}
</style>