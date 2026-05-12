# Tally to ERPNext Migrator

## Introduction

Tally to ERPNext Migrator is a Frappe app that helps migrate Tally Prime data into ERPNext. It uses Tally Definition Language and Frappe REST APIs to transfer master records and transactions from Tally into ERPNext.

## Prerequisites

- TCP file.
- Tally Prime version 7.0 or higher.
- A running Frappe/ERPNext site.

## Version Compatibility

- Tally: Tested with Tally Prime 7.0 and newer.
- ERPNext/Frappe: v15, v16.


## Supported Objects

The app currently supports migrating the following object types:

- Customer
- Supplier
- Contact
- Address
- Item
- Sales Invoice
- Credit Note
- Purchase Invoice
- Debit Note
- Payment Entry
- Journal Entry

## Unsupported Objects

The following Tally objects are not supported by this migration tool:

- Account / Chart of Accounts
- Stock Reconciliation
- Purchase Order / Sales Order
- Manufacturing / Bill of Materials
- Bank Reconciliation
- Tally-specific ledgers or custom masters beyond the supported list

## Installation

### Frappe Cloud

1. Sign up or log in to Frappe Cloud: https://cloud.frappe.io/dashboard/signup?referrer=81385938

### Local Hosted

1. From your local bench folder, get the app:

    ```bash
    bench get-app --branch version-16 https://github.com/eactivelaxman/tally_to_erpnext_migrator.git
    ```

2. Install the app on your site:

    ```bash
    bench --site [site-name] install-app tally_to_erpnext_migrator
    ```

3. Restart bench:

    ```bash
    bench restart
    ```

## Limitations and Points to Remember

- This app does not sync Tally's Chart of Accounts. Account mapping must be handled manually in ERPNext.
- Only the objects listed under "Supported Objects" are migrated reliably.
- Data validation in Tally and ERPNext may differ; review migrated records carefully.
- Use a test site or backup your ERPNext and Tally database before running migrations.
- Large data sets may require multiple batches and performance tuning.
- Custom Tally configurations or custom fields are not automatically migrated.
- Always verify customer, item, and transaction data after migration for correctness.


## License

This project is licensed under the GNU General Public License (v3).
