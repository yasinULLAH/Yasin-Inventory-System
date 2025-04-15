# Offline Inventory & Khata Management System

## Overview

This is a simple, completely offline inventory management and customer ledger (Khata) system built as a single HTML file application. It utilizes HTML, CSS, and JavaScript, storing all data locally in your web browser using IndexedDB. This makes it suitable for small businesses or individuals needing a basic inventory and customer credit tracking tool that works without an internet connection.

## Features

* **Dashboard:** Overview of key metrics like total products, customers, sales, outstanding balance, recent transactions, and low stock items.
* **Inventory Management:**
    * Add, edit, and delete products (Name, SKU, Category, Cost Price, Selling Price, Initial Stock).
    * View current stock levels.
    * Low stock warnings on the dashboard and product table.
    * Search products by name, SKU, or category.
* **Customer Management:**
    * Add, edit, and delete customers (Name, Phone, Email, Address, Notes).
    * Track customer outstanding balances.
    * Search customers by name, phone, or email.
* **Transaction Management:**
    * Record 'Buy' (Stock In) and 'Sell' (Stock Out) transactions.
    * Select products and quantities for each transaction.
    * Automatically updates product stock levels.
    * For sales, select customer (or 'Walk-in') and record amount paid.
    * Automatically calculates and updates customer balance for credit sales.
    * View transaction details.
    * Search transactions.
    * Delete transactions (attempts to roll back stock/balance changes).
* **Customer Khata (Ledger):**
    * View a specific customer's transaction history (sales) and payments.
    * See running balance for the selected customer.
    * Record payments received from customers, updating their balance.
    * Print individual customer Khata.
* **Reporting:**
    * Generate reports: Daily Summary, Date Range, Per Customer, Per Product.
    * View summary statistics (Total Sales, Purchases, Profit, Items Sold) for the report criteria.
    * View detailed transaction lists based on the report type.
    * Print reports.
* **Settings:**
    * Configure Business Name, Contact Info, Address, and Currency Symbol.
    * Upload a Business Logo.
    * Set Low Stock Warning Threshold.
    * Configure Auto Backup interval and enable/disable it.
* **Backup & Restore:**
    * Manually create and download a full data backup as a JSON file.
    * Restore data from a previously downloaded JSON backup file (overwrites current data).
    * Automatic backups to browser's Local Storage at configurable intervals.
* **Offline First:** All data is stored locally in the browser via IndexedDB, allowing the application to function fully offline.

## Technology Stack

* **Frontend:** HTML, CSS, JavaScript (Vanilla JS)
* **Data Storage:** Browser IndexedDB
* **Auto Backup:** Browser Local Storage

## How to Use

1.  Download the `index.html` file.
2.  Open the `index.html` file in a modern web browser (like Chrome, Firefox, Edge, Safari) that supports IndexedDB.
3.  The application will initialize the local database on first run.
4.  Start using the different sections via the sidebar menu.

**Important:** Since data is stored *only* within your browser, clearing your browser's site data for this file **will erase all your inventory and customer information**. Use the Backup feature regularly!

## Data Storage

* All primary data (products, customers, transactions, payments, settings) is stored in the browser's **IndexedDB**. This allows for structured storage and querying offline.
* Automatic backups are stored in the browser's **Local Storage**. Local Storage has size limitations, so rely on manual backups for safety.

## Backup and Restore

* **Manual Backup:** Go to the "Backup & Restore" tab and click "Create Backup". A `.json` file containing all your current data will be downloaded. Keep this file safe.
* **Auto Backup:** The system automatically saves a snapshot to Local Storage periodically (interval configured in Settings). This provides *some* protection against accidental browser closure but is **not a substitute for manual backups**.
* **Restore:** Go to the "Backup & Restore" tab, select a previously saved `.json` backup file using the file input, and click "Restore Data". **Warning:** This will completely overwrite any data currently in the application.

## Contributing

This is a simple project, but feel free to fork it and add features. Some ideas:
* Tax calculation
* Discount options
* More detailed reporting or charts
* User authentication (would require backend changes)
* Improved UI/UX
* Data import from CSV

## License

(No license specified in the original code) Consider adding an open-source license like MIT if you intend to share it publicly.
