Vishakha's Dashboard

This is a responsive dashboard built with HTML5, Tailwind CSS, and Chart.js. It features a sidebar for navigation and multiple sections, including analytics with charts, reports, and user management.

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <title>Vishakha's Dashboard</title>
</head>
<body class="bg-gray-900 text-white">
    <div class="flex h-screen">
        <!-- Sidebar -->
        <nav class="w-64 bg-gray-800 p-6 fixed h-full">
            <h2 class="text-2xl font-bold text-blue-400">Dashboard</h2>
            <ul class="mt-6 space-y-4">
                <li><a href="#home" class="block p-2 hover:bg-blue-500 rounded">Home</a></li>
                <li><a href="#analytics" class="block p-2 hover:bg-blue-500 rounded">Analytics</a></li>
                <li><a href="#reports" class="block p-2 hover:bg-blue-500 rounded">Reports</a></li>
                <li><a href="#users" class="block p-2 hover:bg-blue-500 rounded">Users</a></li>
            </ul>
        </nav>
        
        <!-- Main Content -->
        <div class="ml-64 p-10 w-full">
            <section id="home">
                <h1 class="text-4xl font-bold">Welcome to Vishakha's Dashboard</h1>
                <p class="mt-4">Manage and analyze your data efficiently.</p>
            </section>
            
            <section id="analytics" class="mt-10">
                <h2 class="text-3xl font-bold">Analytics</h2>
                <canvas id="analyticsChart" class="mt-6"></canvas>
                <canvas id="pieChart" class="mt-6"></canvas>
                <canvas id="lineChart" class="mt-6"></canvas>
            </section>
            
            <section id="reports" class="mt-10">
                <h2 class="text-3xl font-bold">Reports</h2>
                <div class="bg-gray-800 p-6 rounded-lg mt-6">
                    <p>Monthly Performance Report</p>
                    <table class="w-full mt-4">
                        <thead>
                            <tr class="text-left">
                                <th class="p-2">Category</th>
                                <th class="p-2">Amount</th>
                                <th class="p-2">Change</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr class="bg-gray-700">
                                <td class="p-2">Sales</td>
                                <td class="p-2">$10,000</td>
                                <td class="p-2 text-green-400">+10%</td>
                            </tr>
                            <tr>
                                <td class="p-2">Expenses</td>
                                <td class="p-2">$4,000</td>
                                <td class="p-2 text-red-400">-5%</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
            
            <section id="users" class="mt-10">
                <h2 class="text-3xl font-bold">Users</h2>
                <p class="mt-4">View and manage user data.</p>
                <div class="bg-gray-800 p-6 rounded-lg mt-6">
                    <table class="w-full text-left">
                        <thead>
                            <tr>
                                <th class="p-2">Name</th>
                                <th class="p-2">Email</th>
                                <th class="p-2">Status</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr class="bg-gray-700">
                                <td class="p-2">Alice Johnson</td>
                                <td class="p-2">alice@example.com</td>
                                <td class="p-2 text-green-400">Active</td>
                            </tr>
                            <tr>
                                <td class="p-2">Bob Smith</td>
                                <td class="p-2">bob@example.com</td>
                                <td class="p-2 text-red-400">Inactive</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
        </div>
    </div>
    
    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        const ctx = document.getElementById('analyticsChart').getContext('2d');
        new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ['January', 'February', 'March', 'April'],
                datasets: [{
                    label: 'Revenue',
                    data: [5000, 7000, 8000, 10000],
                    backgroundColor: 'rgba(59, 130, 246, 0.5)'
                }]
            },
        });
    </script>
</body>
</html>
