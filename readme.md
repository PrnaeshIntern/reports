 ```
# Patient Report Generation System

This is a PHP-based system for generating detailed patient reports based on user-selected criteria. The system uses a MySQL database to store patient data and a combination of PHP and HTML to generate reports.

## Prerequisites

To run this system, you will need the following:

* A web server with PHP and MySQL support
* A MySQL database
* The PHP MySQLi extension

## Installation

1. Clone the repository to your web server.
2. Create a MySQL database and import the `patient_data.sql` file.
3. Configure the database connection settings in the `backup.php` and `backup_main.php` files.
4. Upload the files to your web server.

## Usage

To use the system, follow these steps:

1. Open the `backup_main.php` file in a web browser.
2. Select the desired search criteria from the form.
3. Click the "Generate Report" button.
4. The report will be generated and displayed on the screen.

## Code Explanation

The system consists of two main PHP files: `backup.php` and `backup_main.php`.

### backup.php

This file contains the PHP code to connect to the database, execute the query, and fetch the data. It also includes functions to display the branch, room, and bed data.

```php
// Database connection settings
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "theatgg6_sal_subscriber102";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// User-selected values
$userCountry = "India"; // Replace with user input
$userState = ""; // Replace with user input
$userBranchName = "Pallavaram"; // Replace with user input
$userCity = ""; // Replace with user input
$userRoomId = "139"; // Replace with user input for room_id
$userBedNumber = ""; // Replace with user input for bed_number

// Base SQL query to select branch data with room and bed details
$sql = "SELECT branch.id AS branch_id, branch.branch

Generated by [BlackboxAI](https://www.useblackbox.ai)
