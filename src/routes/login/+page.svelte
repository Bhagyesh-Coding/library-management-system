<script>
	let email = $state('');
	let password = $state('');
</script>

<svelte:head>
	<title>Login | Library Management System</title>
</svelte:head>

<div class="login-page">

	<!-- ================= LEFT PANEL ================= -->
	<section class="left-panel">

		<!-- Background image -->
		<div class="library-background"></div>

		<div class="left-content">

			<div class="logo">
				<span>▤</span>
			</div>

			<h1>Empower Your Library</h1>

			<p class="description">
				Join LibriSystem to streamline your operations and deliver a better
				experience.
			</p>

			<div class="features">

				<div class="feature">
					<div class="feature-icon">▣</div>

					<div>
						<h3>Manage collections anywhere</h3>
						<p>Access and update your catalog from any device, at any time.</p>
					</div>
				</div>

				<div class="feature">
					<div class="feature-icon">♢</div>

					<div>
						<h3>Secure data encryption</h3>
						<p>Your data is protected with industry-leading security protocols.</p>
					</div>
				</div>


				<div class="feature">
					<div class="feature-icon">♧</div>

					<div>
						<h3>Seamless collaboration</h3>
						<p>Work together with your team effortlessly in real-time.</p>
					</div>
				</div>

			</div>

			<div class="copyright">
				© 2026 LibriSystem. All rights reserved.
			</div>

		</div>
	</section>


	<section class="right-panel">

		<div class="login-container">

			<h2>Welcome back</h2>

			<p class="login-subtitle">
				Sign in to your LibriSystem account.
			</p>

			<!-- Login Card -->
			<div class="login-card">

				<form>

					<!-- Email -->
					<div class="form-group">

						<label for="email">EMAIL ADDRESS</label>

						<div class="input-wrapper">

							<span class="input-icon">✉</span>

							<input
								id="email"
								type="email"
								bind:value={email}
								placeholder="admin@librisystem.com"
							/>

						</div>

					</div>

					<!-- Password -->
					<div class="form-group">

						<label for="password">PASSWORD</label>

						<div class="input-wrapper">

							<span class="input-icon">♙</span>

							<input
								id="password"
								type="password"
								bind:value={password}
								placeholder="••••••••"
							/>

						</div>

						<p class="password-hint">
							Must be at least 8 characters.
						</p>

					</div>

					<!-- Login button -->
					<button type="button" class="login-button">
						Sign In
					</button>


					<!-- Terms -->
					<p class="terms">
						By signing in, you agree to our
						<a href="/">Terms of Service</a>
						and
						<a href="/">Privacy Policy</a>.
					</p>

				</form>

			</div>

			<p class="register-text">
				Don't have an account?
				<a href="/register">Create Account</a>
			</p>

		</div>

	</section>

</div>


<style>

	:global(*) {
		box-sizing: border-box;
	}

	:global(body) {
		margin: 0;
		font-family:
			Arial,
			Helvetica,
			sans-serif;
	}

	.login-page {
		min-height: 100vh;

		display: flex;

		background: #ffffff;
	}

	.left-panel {
		position: relative;

		width: 50%;
		min-height: 100vh;

		overflow: hidden;

		background:
			linear-gradient(
				135deg,
				#1765d8 0%,
				#1260d6 45%,
				#1554c2 100%
			);

		color: white;
	}

	.library-background {
		position: absolute;

		inset: 0;

		background-image:
			linear-gradient(
				rgba(22, 100, 215, 0.88),
				rgba(15, 91, 204, 0.94)
			),
			url('https://images.unsplash.com/photo-1521587760476-6c12a4b040da?auto=format&fit=crop&w=1200&q=80');

		background-size: cover;
		background-position: center;

		opacity: 0.7;
	}

	.left-content {
		position: relative;
		z-index: 1;

		min-height: 100vh;

		padding: 44px 12% 30px;

		display: flex;
		flex-direction: column;
	}

	.logo {
		width: 40px;
		height: 40px;

		display: flex;
		align-items: center;
		justify-content: center;

		border-radius: 7px;

		background: rgba(255, 255, 255, 0.14);

		border: 1px solid rgba(255, 255, 255, 0.25);

		box-shadow:
			0 5px 15px rgba(0, 0, 0, 0.12);
	}

	.logo span {
		font-size: 23px;

		color: white;
	}

	.left-content h1 {
		margin: 48px 0 10px;

		font-size: clamp(30px, 3vw, 44px);

		line-height: 1.1;

		font-weight: 700;

		letter-spacing: -1px;
	}

	.description {
		max-width: 470px;

		margin: 0;

		font-size: 13px;

		line-height: 1.6;

		color: rgba(255, 255, 255, 0.92);
	}

	.features {
		margin-top: 30px;

		display: flex;
		flex-direction: column;

		gap: 22px;
	}


	.feature {
		display: flex;

		align-items: flex-start;

		gap: 14px;

		max-width: 480px;
	}


	.feature-icon {
		flex-shrink: 0;

		width: 27px;
		height: 27px;

		display: flex;
		align-items: center;
		justify-content: center;

		border-radius: 5px;

		background: rgba(255, 255, 255, 0.15);

		border: 1px solid rgba(255, 255, 255, 0.15);

		font-size: 13px;
	}


	.feature h3 {
		margin: 0 0 4px;

		font-size: 13px;

		font-weight: 600;
	}


	.feature p {
		margin: 0;

		font-size: 10px;

		line-height: 1.5;

		color: rgba(255, 255, 255, 0.78);
	}

	.copyright {
		margin-top: auto;

		font-size: 10px;

		color: rgba(255, 255, 255, 0.8);
	}

	.right-panel {
		width: 50%;
		min-height: 100vh;

		display: flex;

		align-items: center;
		justify-content: center;

		background: #ffffff;
	}

	.login-container {
		width: 100%;

		max-width: 420px;

		padding: 40px;
	}

	.login-container h2 {
		margin: 0;

		font-size: 25px;

		font-weight: 600;

		color: #171717;
	}


	.login-subtitle {
		margin: 6px 0 20px;

		font-size: 12px;

		color: #777777;
	}

	.login-card {
		width: 100%;

		padding: 22px 20px;

		border: 1px solid #dddddd;

		border-radius: 8px;

		background: #ffffff;

		box-shadow:
			0 5px 15px rgba(0, 0, 0, 0.07);
	}

	.form-group {
		margin-bottom: 17px;
	}


	label {
		display: block;

		margin-bottom: 7px;

		font-size: 8px;

		font-weight: 700;

		letter-spacing: 0.5px;

		color: #333333;
	}

	.input-wrapper {
		position: relative;
	}

	.input-icon {
		position: absolute;

		left: 9px;

		top: 50%;

		transform: translateY(-50%);

		font-size: 11px;

		color: #777777;
	}

	input {
		width: 100%;

		height: 31px;

		padding: 7px 10px 7px 28px;

		border: 1px solid #dddddd;

		border-radius: 3px;

		background: white;

		color: #333333;

		font-size: 10px;

		outline: none;
	}


	input::placeholder {
		color: #999999;
	}


	input:focus {
		border-color: #2468df;

		box-shadow:
			0 0 0 2px rgba(36, 104, 223, 0.08);
	}


	.password-hint {
		margin: 5px 0 0;

		font-size: 8px;

		color: #777777;
	}

	.login-button {
		width: 100%;

		height: 34px;

		margin-top: 3px;

		border: none;

		border-radius: 3px;

		background: #2867dc;

		color: white;

		font-size: 10px;

		font-weight: 600;

		cursor: pointer;

		transition:
			background 0.2s,
			transform 0.2s;
	}


	.login-button:hover {
		background: #1e57c5;

		transform: translateY(-1px);
	}

	.terms {
		margin: 12px 5px 0;

		text-align: center;

		font-size: 7px;

		line-height: 1.5;

		color: #777777;
	}


	.terms a {
		color: #2867dc;

		text-decoration: none;
	}


	.terms a:hover {
		text-decoration: underline;
	}

	.register-text {
		margin: 18px 0 0;

		text-align: center;

		font-size: 10px;

		color: #555555;
	}


	.register-text a {
		color: #1558c7;

		font-weight: 600;

		text-decoration: none;
	}


	.register-text a:hover {
		text-decoration: underline;
	}


	@media (max-width: 800px) {

		.login-page {
			flex-direction: column;
		}

		.left-panel {
			width: 100%;
			min-height: auto;
		}

		.left-content {
			min-height: auto;

			padding: 35px 8%;
		}

		.left-content h1 {
			margin-top: 30px;
		}

		.features {
			gap: 15px;
		}

		.copyright {
			margin-top: 35px;
		}

		.right-panel {
			width: 100%;
			min-height: auto;

			padding: 50px 20px;
		}

		.login-container {
			max-width: 500px;
		}
	}

	@media (max-width: 450px) {

		.login-container {
			padding: 25px 10px;
		}

		.login-card {
			padding: 20px 15px;
		}

		.left-content h1 {
			font-size: 30px;
		}
	}
</style>