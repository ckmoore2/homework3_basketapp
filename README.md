# Basket App with Flask and PostgreSQL

This application is a simple API with a Flask backend and PostgreSQL database. It demonstrates basic database interactions, such as inserting records and fetching unique values from two tables (`basket_a` and `basket_b`). The app is set up to run locally, displaying unique fruits in each basket and allowing for the insertion of new fruits.

## Team Members
- Curtis Moore
- Landon Brown

## Project Setup

**Clone the Repository**:
   https://github.com/ckmoore2/homework3_basketapp.git
   
   cd basket-app

**Install Required Dependencies: Install Python dependencies using pip.

    pip install -r requirements.txt

**Database Setup

    Create PostgreSQL Database:
        Open PostgreSQL and create a database:

CREATE DATABASE homework3;

**Switch to the new database:

    \c homework3

**Create Tables and Insert Data: Run the following SQL commands in PostgreSQL to set up the tables basket_a and basket_b:

CREATE TABLE basket_a (
    a INT PRIMARY KEY,
    fruit_a VARCHAR(100) NOT NULL
);

CREATE TABLE basket_b (
    b INT PRIMARY KEY,
    fruit_b VARCHAR(100) NOT NULL
);

INSERT INTO basket_a (a, fruit_a) VALUES (1, 'Apple'), (2, 'Orange'), (3, 'Banana'), (4, 'Cucumber');
INSERT INTO basket_b (b, fruit_b) VALUES (1, 'Orange'), (2, 'Apple'), (3, 'Watermelon'), (4, 'Pear');

**Configure Database Connection: Update the SQLALCHEMY_DATABASE_URI in app.py with your PostgreSQL username, password, host, and database name:

    app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://<username>:<password>@localhost:5432/homework3'

**Running the Application

    Run the Flask Application: Start the Flask server with:

    python app.py

**Access the Application:
        Insert a New Fruit: Visit http://127.0.0.1:5000/api/update_basket_a to insert a new fruit (Cherry) into basket_a.
        View Unique Fruits: Visit http://127.0.0.1:5000/api/unique to display unique fruits from basket_a and basket_b in an HTML table.

**API Endpoints

    POST /api/update_basket_a: Adds a new fruit (Cherry) to basket_a with ID 5.
        Response:
            Success: "Success!" (status code 200)
            Error: Error message from PostgreSQL (status code 500)

    GET /api/unique: Fetches unique fruits from both basket_a and basket_b and displays them in an HTML table.
        Response:
            HTML table showing unique fruits from each basket.
            Error: Error message from PostgreSQL (status code 500)

Directory Structure

The following is the structure of the repository:

plaintext

basket-app/
├── app.py                  # Main Flask application
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
└── templates/
    └── unique_fruits.html  # HTML template for displaying unique fruits

Example Usage

    Add a New Fruit to Basket A:
        Visit http://127.0.0.1:5000/api/update_basket_a to insert a new fruit into basket_a.
        If successful, you'll see "Success!" in the browser.

    View Unique Fruits:
        Visit http://127.0.0.1:5000/api/unique to view a table with unique fruits from each basket.
