<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Sales</title>
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <style>
        #total-sales {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container my-5">
        <h1 class="text-center">Product Sales</h1>
        <table class="table table-striped table-bordered">
            <thead class="thead-dark">
                <tr>
                    <th>Product</th>
                    <th>Total Sales</th>
                </tr>
            </thead>
            <tbody id="product-sales">
                <!-- Product sales data will be inserted here dynamically -->
            </tbody>
            <tfoot>
                <tr>
                    <td>Total</td>
                    <td id="total-sales">$0.00</td>
                </tr>
            </tfoot>
        </table>
    </div>

    <script>
        async function fetchData() {
            const response = await fetch('data.csv');
            const data = await response.text();
            return data.split('\n').slice(1).map(line => {
                const [product, sales] = line.split(',');
                return { product: product.trim(), sales: parseFloat(sales) };
            });
        }

        async function updateSalesTable() {
            const data = await fetchData();
            const tbody = document.getElementById('product-sales');
            const totalSalesElem = document.getElementById('total-sales');
            let totalSales = 0;

            data.forEach(item => {
                const row = document.createElement('tr');
                const productCell = document.createElement('td');
                const salesCell = document.createElement('td');

                productCell.textContent = item.product;
                salesCell.textContent = `$${item.sales.toFixed(2)}`;

                row.appendChild(productCell);
                row.appendChild(salesCell);

                tbody.appendChild(row);

                totalSales += item.sales;
            });

            totalSalesElem.textContent = `$${totalSales.toFixed(2)}`;
        }

        // On page load, update the sales table
        document.addEventListener('DOMContentLoaded', updateSalesTable);
    </script>
</body>
</html>