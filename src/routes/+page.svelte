<svelte:head>
	<title>LibriSystem - Library Management System</title>
</svelte:head>

<div class="welcome-page">

	<!-- Background decoration -->
	<div class="background-pattern"></div>

	<!-- Main Hero Section -->
	<section class="hero">

		<!-- Book Icon -->
		<div class="icon-box">
			<span>📖</span>
		</div>

		<!-- Main Heading -->
		<h1>
			The Modern Library<br />
			Management System
		</h1>

		<!-- Description -->
		<p class="description">
			LibriSystem streamlines operations, empowers patrons, and provides
			actionable insights for the modern library environment. Secure,
			scalable, and built for the future.
		</p>
		<!-- Get Started Button -->
		<a href="/signup" class="get-started">
			<span>Get Started</span>
			<span class="arrow">→</span>
		</a>

	</section>

	<!-- Bottom Section -->
	<section class="features">

		<h2>Everything you need to manage your collection</h2>

		<p>
			A comprehensive suite of high-performance tools designed specifically
			for enterprise-scale library management.
		</p>

	</section>

</div>


<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: Arial, Helvetica, sans-serif;
		background: #f7f9fc;
	}

	:global(*) {
		box-sizing: border-box;
	}

	.welcome-page {
		min-height: 100vh;
		position: relative;
		overflow: hidden;
		background:
			linear-gradient(
				180deg,
				rgba(248, 250, 253, 0.95),
				rgba(248, 250, 253, 0.98)
			);
		border: 3px solid #6c63e8;
		border-radius: 10px 10px 0 0;
	}

	/* Very light library background */
	.background-pattern {
		position: absolute;
		inset: 0;
		z-index: 0;
		opacity: 0.09;

		background-image:
			linear-gradient(120deg, transparent 45%, #cbd5e1 46%, transparent 47%),
			linear-gradient(60deg, transparent 45%, #cbd5e1 46%, transparent 47%);
		background-size: 220px 220px;
		filter: blur(1px);
	}

	/* Hero */
	.hero {
		position: relative;
		z-index: 1;

		min-height: 510px;

		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;

		padding-top: 105px;
	}

	/* Icon */
	.icon-box {
		width: 53px;
		height: 53px;

		display: flex;
		align-items: center;
		justify-content: center;

		background: white;
		border: 1px solid #dfe4eb;
		border-radius: 10px;

		box-shadow:
			0 4px 10px rgba(0, 0, 0, 0.08),
			0 1px 3px rgba(0, 0, 0, 0.05);

		margin-bottom: 19px;
	}

	.icon-box span {
		font-size: 25px;
	}

	/* Heading */
	h1 {
		margin: 0;

		font-size: 37px;
		font-weight: 400;
		line-height: 1.27;
		letter-spacing: -0.8px;

		color: #111111;
	}

	/* Description */
	.description {
		width: 455px;
		max-width: 90%;

		margin: 12px 0 22px;

		font-size: 14px;
		line-height: 1.55;

		color: #343434;
	}

	/* Button */
	.get-started {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 12px;

		width: 122px;
		height: 37px;

		background: #0757c9;
		color: white;

		text-decoration: none;

		border-radius: 5px;

		font-size: 11px;
		font-weight: bold;

		box-shadow:
			0 3px 6px rgba(0, 0, 0, 0.18),
			inset 0 1px 0 rgba(255, 255, 255, 0.15);

		transition: all 0.2s ease;
	}

	.get-started:hover {
		background: #0049ad;
		transform: translateY(-1px);
		box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
	}

	.arrow {
		font-size: 19px;
		font-weight: normal;
		line-height: 1;
	}

	/* Bottom section */
	.features {
		position: relative;
		z-index: 1;

		text-align: center;

		padding-top: 15px;
		padding-bottom: 60px;
	}

	.features h2 {
		margin: 0 0 7px;

		font-size: 19px;
		font-weight: 600;

		color: #111111;
	}

	.features p {
		width: 440px;
		max-width: 90%;

		margin: 0 auto;

		font-size: 11.5px;
		line-height: 1.5;

		color: #555;
	}


	/* Responsive */
	@media (max-width: 600px) {

		.hero {
			padding-top: 70px;
			min-height: 480px;
		}

		h1 {
			font-size: 30px;
		}

		.description {
			width: 90%;
			font-size: 13px;
		}

		.features h2 {
			font-size: 17px;
			padding: 0 15px;
		}

		.features p {
			width: 90%;
		}
	}
</style>