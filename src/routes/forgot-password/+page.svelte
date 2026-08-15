<script>
	let email = '';
	let newPassword = '';
	let confirmPassword = '';
</script>

<svelte:head>
	<title>Forgot Password | Library Management System</title>
</svelte:head>

<div class="forgot-page">

	<!-- ================= LEFT PANEL ================= -->
	<section class="left-panel">

		<div class="library-background"></div>

		<div class="left-content">

			<!-- Logo -->
			<div class="logo">
				<span>▤</span>
			</div>

			<!-- Heading -->
			<h1>Empower Your Library</h1>

			<p class="description">
				Join LibriSystem to streamline your operations and deliver a better
				experience.
			</p>

			<!-- Features -->
			<div class="features">

				<div class="feature">
					<div class="feature-icon">▣</div>

					<div>
						<h3>Manage collections anywhere</h3>
						<p>
							Access and update your catalog from any device, at any time.
						</p>
					</div>
				</div>

				<div class="feature">
					<div class="feature-icon">♢</div>

					<div>
						<h3>Secure data encryption</h3>
						<p>
							Your data is protected with industry-leading security protocols.
						</p>
					</div>
				</div>

				<div class="feature">
					<div class="feature-icon">♧</div>

					<div>
						<h3>Seamless collaboration</h3>
						<p>
							Work together with your team effortlessly in real-time.
						</p>
					</div>
				</div>

			</div>

			<!-- Copyright -->
			<div class="copyright">
				© 2026 LibriSystem. All rights reserved.
			</div>

		</div>
	</section>


	<!-- ================= RIGHT PANEL ================= -->
	<section class="right-panel">

		<div class="forgot-container">

			<h2>Reset your password</h2>

			<p class="forgot-subtitle">
				Enter your details to create a new password.
			</p>


			<!-- Reset Password Card -->
			<div class="forgot-card">

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
								placeholder="Enter your email"
							/>

						</div>

					</div>


					<!-- New Password -->
					<div class="form-group">

						<label for="new-password">NEW PASSWORD</label>

						<div class="input-wrapper">

							<span class="input-icon">♙</span>

							<input
								id="new-password"
								type="password"
								bind:value={newPassword}
								placeholder="Enter new password"
							/>

						</div>

						<p class="password-hint">
							Must be at least 8 characters.
						</p>

					</div>


					<!-- Confirm Password -->
					<div class="form-group">

						<label for="confirm-password">CONFIRM PASSWORD</label>

						<div class="input-wrapper">

							<span class="input-icon">♙</span>

							<input
								id="confirm-password"
								type="password"
								bind:value={confirmPassword}
								placeholder="Confirm new password"
							/>

						</div>

					</div>


					<!-- Reset Button -->
					<button type="button" class="reset-button">
						Reset Password
					</button>


					<!-- Information -->
					<p class="terms">
						Make sure your new password is secure and easy for you to remember.
					</p>

				</form>

			</div>


			<!-- Back to Login -->
			<p class="login-text">
				Remember your password?
				<a href="/login">Sign In</a>
			</p>

		</div>

	</section>

</div>


<style>
	/* ================================
	   RESET
	================================ */

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


	/* ================================
	   MAIN PAGE
	================================ */

	.forgot-page {
		min-height: 100vh;

		display: flex;

		background: #ffffff;
	}


	/* ================================
	   LEFT PANEL
	================================ */

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


	/* ================================
	   LOGO
	================================ */

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


	/* ================================
	   LEFT HEADING
	================================ */

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


	/* ================================
	   FEATURES
	================================ */

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


	/* ================================
	   COPYRIGHT
	================================ */

	.copyright {
		margin-top: auto;

		font-size: 10px;

		color: rgba(255, 255, 255, 0.8);
	}


	/* ================================
	   RIGHT PANEL
	================================ */

	.right-panel {
		width: 50%;
		min-height: 100vh;

		display: flex;

		align-items: center;
		justify-content: center;

		background: #ffffff;
	}


	.forgot-container {
		width: 100%;

		max-width: 420px;

		padding: 40px;
	}


	/* ================================
	   HEADING
	================================ */

	.forgot-container h2 {
		margin: 0;

		font-size: 25px;

		font-weight: 600;

		color: #171717;
	}


	.forgot-subtitle {
		margin: 6px 0 20px;

		font-size: 12px;

		color: #777777;
	}


	/* ================================
	   CARD
	================================ */

	.forgot-card {
		width: 100%;

		padding: 22px 20px;

		border: 1px solid #dddddd;

		border-radius: 8px;

		background: #ffffff;

		box-shadow:
			0 5px 15px rgba(0, 0, 0, 0.07);
	}


	/* ================================
	   FORM
	================================ */

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


	/* ================================
	   PASSWORD HINT
	================================ */

	.password-hint {
		margin: 5px 0 0;

		font-size: 8px;

		color: #777777;
	}


	/* ================================
	   RESET BUTTON
	================================ */

	.reset-button {
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


	.reset-button:hover {
		background: #1e57c5;

		transform: translateY(-1px);
	}


	/* ================================
	   INFORMATION
	================================ */

	.terms {
		margin: 12px 5px 0;

		text-align: center;

		font-size: 7px;

		line-height: 1.5;

		color: #777777;
	}


	/* ================================
	   LOGIN LINK
	================================ */

	.login-text {
		margin: 18px 0 0;

		text-align: center;

		font-size: 10px;

		color: #555555;
	}


	.login-text a {
		color: #1558c7;

		font-weight: 600;

		text-decoration: none;
	}


	.login-text a:hover {
		text-decoration: underline;
	}


	/* ================================
	   RESPONSIVE
	================================ */

	@media (max-width: 800px) {

		.forgot-page {
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

		.forgot-container {
			max-width: 500px;
		}
	}


	@media (max-width: 450px) {

		.forgot-container {
			padding: 25px 10px;
		}

		.forgot-card {
			padding: 20px 15px;
		}

		.left-content h1 {
			font-size: 30px;
		}
	}
</style>