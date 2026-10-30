HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 8.4 — Dashboard with Grid and Flexbox</title>
    <!-- Link to External Stylesheet -->
    <link rel="stylesheet" href="combined-style.css">
</head>
<body>

    <!-- --- 2. Outer Page Layout (CSS Grid) --- -->
    <div class="dashboard-layout">

        <!-- --- 1. Dashboard Header --- -->
        <header class="dash-header">
            <div class="logo-area">AdminMaster</div>
            <div class="user-profile">
                <span>Welcome, Student</span>
            </div>
        </header>

        <!-- --- 1. Sidebar Navigation --- -->
        <aside class="dash-sidebar">
            <ul class="nav-list">
                <li><a href="#" class="active">Dashboard</a></li>
                <li><a href="#">Analytics</a></li>
                <li><a href="#">Transactions</a></li>
                <li><a href="#">Settings</a></li>
                <li><a href="#">Logout</a></li>
            </ul>
        </aside>

        <!-- --- 1 & 3. Main Content Area & 4 Statistic Cards --- -->
        <main class="dash-main">
            <div class="main-title">
                <h1>Dashboard Overview</h1>
                <p>Monitor your core platform metrics and recent activities.</p>
            </div>

            <!-- Statistic Cards Container -->
            <div class="stats-container">
                
                <!-- Card 1 -->
                <div class="stat-card">
                    <div class="card-icon revenue-icon">💰</div>
                    <div class="card-info">
                        <h3>Total Revenue</h3>
                        <p class="card-number">$45,280</p>
                        <span class="trend positive">+15% this month</span>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="stat-card">
                    <div class="card-icon users-icon">👥</div>
                    <div class="card-info">
                        <h3>Active Users</h3>
                        <p class="card-number">2,415</p>
                        <span class="trend positive">+8% vs last week</span>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="stat-card">
                    <div class="card-icon orders-icon">📦</div>
                    <div class="card-info">
                        <h3>Pending Orders</h3>
                        <p class="card-number">38</p>
                        <span class="trend negative">-3% processing</span>
                    </div>
                </div>

                <!-- Card 4 -->
                <div class="stat-card">
                    <div class="card-icon growth-icon">📈</div>
                    <div class="card-info">
                        <h3>Conversion Rate</h3>
                        <p class="card-number">4.2%</p>
                        <span class="trend positive">+1.2% growth</span>
                    </div>
                </div>

            </div>

            <!-- --- 5. Recent Activity / Table Section --- -->
            <section class="activity-section">
                <h2>Recent Transactions</h2>
                <div class="table-responsive">
                    <table class="activity-table">
                        <thead>
                            <tr>
                                <th>Transaction ID</th>
                                <th>Customer</th>
                                <th>Date</th>
                                <th>Amount</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>#TXN-9841</td>
                                <td>Sarah Jenkins</td>
                                <td>Oct 30, 2026</td>
                                <td>$250.00</td>
                                <td><span class="badge success">Completed</span></td>
                            </tr>
                            <tr>
                                <td>#TXN-9842</td>
                                <td>Michael Chang</td>
                                <td>Oct 30, 2026</td>
                                <td>$120.50</td>
                                <td><span class="badge success">Completed</span></td>
                            </tr>
                            <tr>
                                <td>#TXN-9843</td>
                                <td>Amanda Smith</td>
                                <td>Oct 29, 2026</td>
                                <td>$430.00</td>
                                <td><span class="badge warning">Pending</span></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
        </main>

    </div>

</body>
</html>
File 2: combined-style.css
CSS
/* --- Global Reset & Design Tokens --- */
:root {
    --primary-color: #1e3a8a;
    --secondary-color: #2563eb;
    --bg-color: #f8fafc;
    --card-bg: #ffffff;
    --text-main: #1e293b;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-main);
}

/* ==========================================
   2. OUTER PAGE LAYOUT (CSS Grid)
   ================================---------- */
.dashboard-layout {
    display: grid;                          /* Enable CSS Grid */
    grid-template-columns: 260px 1fr;       /* Sidebar (260px) and Main Content (1fr) */
    grid-template-rows: 70px 1fr;           /* Header (70px) and Content */
    min-height: 100vh;
}

/* --- Header Section (Grid Item) --- */
.dash-header {
    grid-column: 1 / -1;                    /* Spans full width across columns */
    background-color: var(--card-bg);
    border-bottom: 1px solid var(--border-color);
    display: flex;                          /* Inner Flexbox for header items */
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;
    z-index: 10;
}

.logo-area {
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--primary-color);
}

.user-profile {
    font-weight: 600;
    color: var(--text-muted);
    font-size: 0.95rem;
}

/* --- Sidebar Section (Grid Item) --- */
.dash-sidebar {
    background-color: #0f172a;
    color: #ffffff;
    padding: 2rem 1rem;
    border-right: 1px solid var(--border-color);
}

.nav-list {
    list-style: none;
    display: flex;                          /* Inner Flexbox for sidebar links */
    flex-direction: column;
    gap: 0.75rem;
}

.nav-list a {
    display: block;
    color: #94a3b8;
    text-decoration: none;
    padding: 0.75rem 1rem;
    border-radius: 6px;
    font-weight: 500;
    transition: background-color 0.2s ease, color 0.2s ease;
}

.nav-list a:hover,
.nav-list a.active {
    background-color: var(--secondary-color);
    color: #ffffff;
}

/* --- Main Content Section (Grid Item) --- */
.dash-main {
    padding: 2.5rem;
    overflow-y: auto;
}

.main-title {
    margin-bottom: 2rem;
}

.main-title h1 {
    font-size: 1.8rem;
    color: var(--primary-color);
    margin-bottom: 0.25rem;
}

.main-title p {
    color: var(--text-muted);
}

/* ==========================================
   3 & 4. STATISTIC CARDS (Inner Flexbox)
   ================================---------- */
.stats-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
    margin-bottom: 2.5rem;
}

.stat-card {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    padding: 1.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02);
    
    /* 4. Inner Flexbox layout for card contents */
    display: flex;
    align-items: center;
    gap: 1.25rem;
}

.card-icon {
    font-size: 2rem;
    background-color: #f1f5f9;
    width: 55px;
    height: 55px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
}

.card-info {
    display: flex;
    flex-direction: column;
}

.card-info h3 {
    font-size: 0.85rem;
    color: var(--text-muted);
    font-weight: 600;
    text-transform: uppercase;
}

.card-number {
    font-size: 1.6rem;
    font-weight: 700;
    color: var(--primary-color);
    margin: 0.2rem 0;
}

.trend {
    font-size: 0.8rem;
    font-weight: 600;
}

.trend.positive { color: #16a34a; }
.trend.negative { color: #dc2626; }

/* ==========================================
   5. RECENT ACTIVITY TABLE SECTION
   ================================---------- */
.activity-section {
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    padding: 1.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02);
}

.activity-section h2 {
    font-size: 1.25rem;
    color: var(--primary-color);
    margin-bottom: 1.25rem;
}

.table-responsive {
    overflow-x: auto;
}

.activity-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 0.95rem;
    text-align: left;
}

.activity-table th,
.activity-table td {
    padding: 0.85rem 1rem;
    border-bottom: 1px solid var(--border-color);
}

.activity-table th {
    background-color: #f1f5f9;
    color: var(--primary-color);
    font-weight: 600;
}

.activity-table tr:hover {
    background-color: #f8fafc;
}

.badge {
    display: inline-block;
    padding: 0.25rem 0.6rem;
    font-size: 0.75rem;
    font-weight: 700;
    border-radius: 50px;
    text-transform: uppercase;
}

.badge.success {
    background-color: #dcfce7;
    color: #166534;
}

.badge.warning {
    background-color: #fef3c7;
    color: #92400e;
}