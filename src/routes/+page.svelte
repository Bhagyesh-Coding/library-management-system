<svelte:head>
	<title>Library Management System</title>
</svelte:head>

<div class="app">

	<!-- Top Bar -->
	<header>
		<div class="logo">
			<span>📚</span>
			<strong>LIBRARY MANAGEMENT SYSTEM</strong>
		</div>

		<div class="nav-buttons">
			<a href="/login">Login</a>
			<a href="/register" class="register">Register</a>
		</div>
	</header>


	<!-- Main Welcome Area -->
	<main>

		<div class="book-icon">📚</div>

		<h1>Library Management System</h1>

		<p class="intro">
			Manage your library efficiently and easily.
		</p>

		<div class="actions">
			<a href="/login" class="login-btn">Login</a>
			<a href="/register" class="register-btn">Register</a>
		</div>


		<!-- Features -->
		<div class="features">

			<div class="feature">
				<div class="icon">📚</div>
				<div>
					<h3>Books</h3>
					<p>Manage your book collection</p>
				</div>
			</div>

			<div class="feature">
				<div class="icon">👥</div>
				<div>
					<h3>Members</h3>
					<p>Manage library members</p>
				</div>
			</div>

			<div class="feature">
				<div class="icon">🔄</div>
				<div>
					<h3>Issue & Return</h3>
					<p>Track book transactions</p>
				</div>
			</div>

		</div>

		<div class="bottom-text">
			Simple • Fast • Organized
		</div>

	</main>

</div>


<style>

	/* Basic setup */

	:global(*) {
		box-sizing: border-box;
	}

	:global(body) {
		margin: 0;
		font-family: Arial, sans-serif;
		background: #eef3f8;
		color: #1e293b;
	}


	/* Application container */

	.app {
		min-height: 100vh;
	}


	/* Header */

	header {
		height: 70px;
		padding: 0 7%;
		background: white;
		border-bottom: 1px solid #dbe3ec;

		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.logo {
		display: flex;
		align-items: center;
		gap: 10px;
		font-size: 16px;
	}

	.logo span {
		font-size: 24px;
	}

	.nav-buttons {
		display: flex;
		align-items: center;
		gap: 22px;
	}

	.nav-buttons a {
		text-decoration: none;
		color: #334155;
		font-size: 14px;
	}

	.register {
		background: #2563eb;
		color: white !important;
		padding: 9px 16px;
		border-radius: 6px;
	}


	/* Main */

	main {
		max-width: 1000px;
		margin: auto;
		text-align: center;
		padding: 75px 20px;
	}


	/* Welcome */

	.book-icon {
		width: 75px;
		height: 75px;
		margin: auto;

		display: grid;
		place-items: center;

		font-size: 38px;
		background: #dbeafe;
		border-radius: 18px;
	}

	h1 {
		margin: 25px 0 10px;
		font-size: 38px;
		color: #172554;
		text-transform: uppercase;
	}

	.intro {
		margin: 0;
		color: #64748b;
		font-size: 17px;
	}


	/* Buttons */

	.actions {
		display: flex;
		justify-content: center;
		gap: 15px;
		margin: 30px 0 60px;
	}

	.actions a {
		text-decoration: none;
		padding: 12px 30px;
		border-radius: 7px;
		font-weight: bold;
		font-size: 14px;
	}

	.login-btn {
		background: #2563eb;
		color: white;
	}

	.register-btn {
		background: white;
		color: #2563eb;
		border: 1px solid #2563eb;
	}


	/* Feature cards */

	.features {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 20px;
		text-align: left;
	}

	.feature {
		background: white;
		border: 1px solid #dbe3ec;
		border-radius: 10px;
		padding: 22px;

		display: flex;
		align-items: center;
		gap: 15px;

		transition: 0.2s;
	}

	.feature:hover {
		transform: translateY(-3px);
		box-shadow: 0 8px 20px #00000010;
	}

	.icon {
		width: 48px;
		height: 48px;

		display: grid;
		place-items: center;

		background: #eff6ff;
		border-radius: 10px;
		font-size: 23px;
	}

	.feature h3 {
		margin: 0 0 5px;
		font-size: 16px;
	}

	.feature p {
		margin: 0;
		color: #64748b;
		font-size: 12px;
	}


	/* Bottom */

	.bottom-text {
		margin-top: 50px;
		color: #94a3b8;
		font-size: 13px;
		letter-spacing: 1px;
	}


	/* Mobile */

	@media (max-width: 700px) {

		header {
			padding: 0 20px;
		}

		.logo strong {
			font-size: 12px;
		}

		main {
			padding: 50px 20px;
		}

		h1 {
			font-size: 28px;
		}

		.features {
			grid-template-columns: 1fr;
		}
	}

</style>