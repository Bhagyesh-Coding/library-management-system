<script>
	import { onMount } from 'svelte';

	let activeMenu = $state('dashboard');
	let userRole = $state('Library Admin');
	let userBranch = $state('Central Branch');

	// Metric data
	let metrics = $state({
		activeLoans: { value: 1248, change: 12, period: 'last week' },
		overdueItems: { value: 84, change: -5, period: 'last week' },
		totalMembers: { value: 5092, change: 2, period: 'last month' },
		revenue: { value: '₹342.50', change: 0, period: 'Current billing cycle' }
	});

	// Recent activity data
	let activities = $state([
		{
			id: 1,
			item: 'The Great Gatsby',
			itemId: 'PID: #220',
			user: 'John Doe',
			action: 'Checked Out',
			time: '10 mins ago',
			status: 'Success'
		},
		{
			id: 2,
			item: 'Item',
			itemId: 'PID: #102',
			user: 'Jane Smith',
			action: 'Returned',
			time: '25 mins ago',
			status: 'Success'
		},
		{
			id: 3,
			item: 'New Member Registration',
			itemId: '',
			user: 'Alice Johnson',
			action: 'Account Created',
			time: '1 hour ago',
			status: 'Pending ID'
		},
		{
			id: 4,
			item: 'Dune',
			itemId: '#ID: 8831',
			user: 'Mark Lee',
			action: 'Hold Placed',
			time: '2 hours ago',
			status: 'Active'
		}
	]);

	// Quick actions
	let quickActions = [
		{ icon: '↩', title: 'Process Return', subtitle: 'Scan item barcode' },
		{ icon: '👤', title: 'Register Member', subtitle: 'Create new library account' },
		{ icon: '🔍', title: 'Catalog Search', subtitle: 'Find titles or ISBNs' }
	];

	// Menu items
	let menuItems = [
		{ id: 'dashboard', label: 'Dashboard', icon: '📊' },
		{ id: 'inventory', label: 'Inventory', icon: '📚' },
		{ id: 'members', label: 'Members', icon: '👥' },
		{ id: 'settings', label: 'Settings', icon: '⚙' }
	];

	function handleMenuClick(menuId) {
		activeMenu = menuId;
	}

	function handleNewEntry() {
		console.log('New Entry clicked');
	}

	function handleExportReport() {
		console.log('Export Report clicked');
	}
</script>

<svelte:head>
	<title>Dashboard | LibriSystem</title>
</svelte:head>

<div class="dashboard-container">
	<!-- Sidebar -->
	<aside class="sidebar">
		<div class="sidebar-header">
			<div class="logo">▤</div>
			<h1>LibriSystem</h1>
		</div>

		<nav class="sidebar-nav">
			{#each menuItems as item (item.id)}
				<button
					class="nav-item {activeMenu === item.id ? 'active' : ''}"
					on:click={() => handleMenuClick(item.id)}
					aria-current={activeMenu === item.id ? 'page' : undefined}
				>
					<span class="nav-icon">{item.icon}</span>
					<span>{item.label}</span>
				</button>
			{/each}
		</nav>

		<button class="new-entry-btn" on:click={handleNewEntry}>
			+ New Entry
		</button>

		<div class="sidebar-footer">
			<div class="user-info">
				<div class="user-avatar">👤</div>
				<div>
					<p class="user-role">{userRole}</p>
					<p class="user-branch">{userBranch}</p>
				</div>
			</div>

			<button class="footer-link">
				<span>❓</span> Help Center
			</button>
			<button class="footer-link">
				<span>🚪</span> Logout
			</button>
		</div>
	</aside>

	<!-- Main Content -->
	<main class="main-content">
		<!-- Header -->
		<div class="header">
			<div class="header-left">
				<h2>System Dashboard</h2>
				<p class="header-subtitle">Central Branch Overview • Today, Oct 24</p>
			</div>
			<button class="export-btn" on:click={handleExportReport}>
				Export Report
			</button>
		</div>

		<!-- Metrics -->
		<div class="metrics-grid">
			<div class="metric-card">
				<div class="metric-header">
					<h3>Active Loans</h3>
					<span class="metric-icon">📋</span>
				</div>
				<div class="metric-value">1,248</div>
				<div class="metric-change positive">↑ +12% vs last week</div>
			</div>

			<div class="metric-card">
				<div class="metric-header">
					<h3>Overdue Items</h3>
					<span class="metric-icon warning">⚠</span>
				</div>
				<div class="metric-value">84</div>
				<div class="metric-change negative">↓ -5% vs last week</div>
			</div>

			<div class="metric-card">
				<div class="metric-header">
					<h3>Total Members</h3>
					<span class="metric-icon">👥</span>
				</div>
				<div class="metric-value">5,092</div>
				<div class="metric-change positive">↑ +2% vs last month</div>
			</div>

			<div class="metric-card">
				<div class="metric-header">
					<h3>Revenue (Fines)</h3>
					<span class="metric-icon">💰</span>
				</div>
				<div class="metric-value">₹342.50</div>
				<div class="metric-change neutral">Current billing cycle</div>
			</div>
		</div>

		<!-- Content Grid -->
		<div class="content-grid">
			<!-- Recent Activity -->
			<section class="recent-activity">
				<div class="section-header">
					<h3>Recent Activity</h3>
					<a href="#" class="view-all">View All</a>
				</div>

				<div class="activity-table">
					<div class="table-header">
						<div class="col-item">ITEM/USER</div>
						<div class="col-action">ACTION</div>
						<div class="col-time">TIME</div>
						<div class="col-status">STATUS</div>
					</div>

					{#each activities as activity (activity.id)}
						<div class="table-row">
							<div class="col-item">
								<div class="item-name">{activity.item}</div>
								{#if activity.itemId}
									<div class="item-id">{activity.itemId}</div>
								{/if}
								<div class="item-user">{activity.user}</div>
							</div>
							<div class="col-action">{activity.action}</div>
							<div class="col-time">{activity.time}</div>
							<div class="col-status">
								<span class="status-badge {activity.status.toLowerCase().replace(' ', '-')}">
									{activity.status}
								</span>
							</div>
						</div>
					{/each}
				</div>
			</section>

			<!-- Quick Actions -->
			<section class="quick-actions">
				<h3>Quick Actions</h3>

				<div class="actions-list">
					{#each quickActions as action (action.title)}
						<button class="action-item">
							<div class="action-icon">{action.icon}</div>
							<div class="action-content">
								<div class="action-title">{action.title}</div>
								<div class="action-subtitle">{action.subtitle}</div>
							</div>
						</button>
					{/each}
				</div>
			</section>
		</div>
	</main>
</div>

<style>
	:global(*) {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
	}

	:global(body) {
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
			'Helvetica Neue', Arial, sans-serif;
		background: #f5f5f5;
		color: #333;
	}

	.dashboard-container {
		display: flex;
		min-height: 100vh;
	}

	/* Sidebar */
	.sidebar {
		width: 200px;
		background: #f8f9fa;
		border-right: 1px solid #e0e0e0;
		display: flex;
		flex-direction: column;
		overflow-y: auto;
	}

	.sidebar-header {
		padding: 20px;
		display: flex;
		align-items: center;
		gap: 12px;
		border-bottom: 1px solid #e0e0e0;
	}

	.logo {
		width: 32px;
		height: 32px;
		background: #2867dc;
		color: white;
		border-radius: 6px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 18px;
		font-weight: bold;
	}

	.sidebar-header h1 {
		font-size: 16px;
		font-weight: 600;
		color: #333;
	}

	.sidebar-nav {
		flex: 1;
		padding: 10px 0;
		display: flex;
		flex-direction: column;
	}

	.nav-item {
		padding: 12px 20px;
		background: none;
		border: none;
		text-align: left;
		cursor: pointer;
		display: flex;
		align-items: center;
		gap: 12px;
		color: #666;
		font-size: 13px;
		font-weight: 500;
		transition: all 0.2s;
	}

	.nav-item:hover {
		background: #e3e8f3;
		color: #2867dc;
	}

	.nav-item.active {
		background: #e3e8f3;
		color: #2867dc;
		border-left: 3px solid #2867dc;
		padding-left: 17px;
	}

	.nav-icon {
		font-size: 16px;
	}

	.new-entry-btn {
		margin: 20px;
		padding: 10px;
		background: #2867dc;
		color: white;
		border: none;
		border-radius: 4px;
		font-size: 12px;
		font-weight: 600;
		cursor: pointer;
		transition: background 0.2s;
	}

	.new-entry-btn:hover {
		background: #1e57c5;
	}

	.sidebar-footer {
		border-top: 1px solid #e0e0e0;
		padding: 20px;
	}

	.user-info {
		display: flex;
		gap: 12px;
		margin-bottom: 20px;
	}

	.user-avatar {
		width: 40px;
		height: 40px;
		background: #e0e0e0;
		border-radius: 4px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 20px;
	}

	.user-role {
		font-size: 11px;
		font-weight: 600;
		color: #333;
		margin-bottom: 2px;
	}

	.user-branch {
		font-size: 10px;
		color: #999;
	}

	.footer-link {
		width: 100%;
		padding: 8px 0;
		background: none;
		border: none;
		cursor: pointer;
		font-size: 11px;
		color: #666;
		text-align: left;
		display: flex;
		align-items: center;
		gap: 8px;
		transition: color 0.2s;
	}

	.footer-link:hover {
		color: #2867dc;
	}

	/* Main Content */
	.main-content {
		flex: 1;
		padding: 40px;
		overflow-y: auto;
	}

	.header {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: 30px;
	}

	.header-left h2 {
		font-size: 28px;
		font-weight: 600;
		color: #171717;
		margin-bottom: 6px;
	}

	.header-subtitle {
		font-size: 12px;
		color: #999;
	}

	.export-btn {
		padding: 8px 16px;
		background: white;
		border: 1px solid #ddd;
		border-radius: 4px;
		cursor: pointer;
		font-size: 11px;
		font-weight: 600;
		color: #333;
		transition: all 0.2s;
	}

	.export-btn:hover {
		background: #f9f9f9;
		border-color: #999;
	}

	/* Metrics Grid */
	.metrics-grid {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 16px;
		margin-bottom: 30px;
	}

	.metric-card {
		background: white;
		padding: 20px;
		border-radius: 8px;
		border: 1px solid #e0e0e0;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
	}

	.metric-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 12px;
	}

	.metric-header h3 {
		font-size: 11px;
		font-weight: 600;
		color: #666;
		text-transform: uppercase;
		letter-spacing: 0.3px;
	}

	.metric-icon {
		font-size: 18px;
	}

	.metric-icon.warning {
		color: #ff6b6b;
	}

	.metric-value {
		font-size: 28px;
		font-weight: 700;
		color: #171717;
		margin-bottom: 8px;
	}

	.metric-change {
		font-size: 11px;
		font-weight: 500;
	}

	.metric-change.positive {
		color: #22c55e;
	}

	.metric-change.negative {
		color: #ef4444;
	}

	.metric-change.neutral {
		color: #999;
	}

	/* Content Grid */
	.content-grid {
		display: grid;
		grid-template-columns: 1fr 300px;
		gap: 20px;
	}

	/* Recent Activity */
	.recent-activity {
		background: white;
		border-radius: 8px;
		border: 1px solid #e0e0e0;
		overflow: hidden;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
	}

	.section-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 20px;
		border-bottom: 1px solid #e0e0e0;
	}

	.section-header h3 {
		font-size: 14px;
		font-weight: 600;
		color: #171717;
	}

	.view-all {
		font-size: 11px;
		color: #2867dc;
		text-decoration: none;
		font-weight: 600;
		transition: color 0.2s;
	}

	.view-all:hover {
		color: #1e57c5;
	}

	.activity-table {
		padding: 0;
	}

	.table-header {
		display: grid;
		grid-template-columns: 2fr 1.2fr 1fr 0.8fr;
		gap: 12px;
		padding: 12px 20px;
		background: #fafafa;
		border-bottom: 1px solid #e0e0e0;
		font-size: 8px;
		font-weight: 700;
		color: #666;
		text-transform: uppercase;
		letter-spacing: 0.3px;
	}

	.table-row {
		display: grid;
		grid-template-columns: 2fr 1.2fr 1fr 0.8fr;
		gap: 12px;
		padding: 16px 20px;
		border-bottom: 1px solid #e0e0e0;
		align-items: center;
		transition: background 0.2s;
	}

	.table-row:hover {
		background: #fafafa;
	}

	.table-row:last-child {
		border-bottom: none;
	}

	.col-item {
		font-size: 11px;
	}

	.item-name {
		font-weight: 600;
		color: #2867dc;
		margin-bottom: 2px;
	}

	.item-id {
		font-size: 9px;
		color: #999;
		margin-bottom: 4px;
	}

	.item-user {
		font-size: 10px;
		color: #666;
	}

	.col-action {
		font-size: 11px;
		color: #333;
	}

	.col-time {
		font-size: 11px;
		color: #666;
	}

	.col-status {
		text-align: right;
	}

	.status-badge {
		display: inline-block;
		padding: 4px 8px;
		border-radius: 3px;
		font-size: 8px;
		font-weight: 600;
		text-transform: uppercase;
		letter-spacing: 0.2px;
	}

	.status-badge.success {
		background: #dcfce7;
		color: #166534;
	}

	.status-badge.pending-id {
		background: #fef3c7;
		color: #92400e;
	}

	.status-badge.active {
		background: #e0f2fe;
		color: #0c4a6e;
	}

	/* Quick Actions */
	.quick-actions {
		background: white;
		border-radius: 8px;
		border: 1px solid #e0e0e0;
		padding: 20px;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
	}

	.quick-actions h3 {
		font-size: 14px;
		font-weight: 600;
		color: #171717;
		margin-bottom: 16px;
	}

	.actions-list {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.action-item {
		display: flex;
		align-items: flex-start;
		gap: 12px;
		padding: 12px;
		background: #f8f9fa;
		border: none;
		border-radius: 6px;
		cursor: pointer;
		transition: all 0.2s;
		text-align: left;
	}

	.action-item:hover {
		background: #e3e8f3;
		transform: translateX(4px);
	}

	.action-icon {
		font-size: 20px;
		flex-shrink: 0;
		width: 28px;
		height: 28px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.action-content {
		flex: 1;
		min-width: 0;
	}

	.action-title {
		font-size: 11px;
		font-weight: 600;
		color: #333;
		margin-bottom: 2px;
	}

	.action-subtitle {
		font-size: 9px;
		color: #999;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	/* Responsive */
	@media (max-width: 1200px) {
		.metrics-grid {
			grid-template-columns: repeat(2, 1fr);
		}

		.table-header,
		.table-row {
			grid-template-columns: 1.5fr 1fr 0.8fr 0.8fr;
		}
	}

	@media (max-width: 768px) {
		.dashboard-container {
			flex-direction: column;
		}

		.sidebar {
			width: 100%;
			flex-direction: row;
			align-items: center;
			height: auto;
			padding: 10px 20px;
		}

		.sidebar-header {
			padding: 0;
			border: none;
		}

		.sidebar-nav {
			flex-direction: row;
			gap: 0;
			flex: 1;
			margin: 0 20px;
		}

		.nav-item {
			flex: 1;
			padding: 10px;
		}

		.sidebar-footer {
			border: none;
			padding: 0;
			display: flex;
			gap: 10px;
		}

		.user-info,
		.footer-link {
			display: none;
		}

		.main-content {
			padding: 20px;
		}

		.metrics-grid {
			grid-template-columns: repeat(2, 1fr);
			gap: 12px;
		}

		.content-grid {
			grid-template-columns: 1fr;
		}

		.metric-card {
			padding: 15px;
		}

		.metric-value {
			font-size: 22px;
		}
	}

	@media (max-width: 480px) {
		.metrics-grid {
			grid-template-columns: 1fr;
		}

		.header {
			flex-direction: column;
			gap: 15px;
		}

		.main-content {
			padding: 15px;
		}

		.table-header,
		.table-row {
			grid-template-columns: 1fr;
			gap: 8px;
		}

		.section-header {
			padding: 15px;
		}
	}
</style>