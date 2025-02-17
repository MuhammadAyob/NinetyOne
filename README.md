## Solution Overview

This solution  processes test scores from a spreadsheet, stores them securely in a SQLite database, and makes them easily accessible through a locally hosted API through the browser.

Please have a look at the .ipynb file for the outputs and results of the code. 

Feel free to simply download the 'Ninety_One_Graduate_SE.ipynb' file along with the TestData.csv file to run in your environment. In this case I used google colab. The file will also include the output and results of the code without you needing to run it.

## 1. The Approach

This system is designed for simplicity and reliability:

## Manually Reads CSV Files
The system does not use CSV libraries; instead, it manually processes the spreadsheet by reading and splitting the file line by line.

## Stores Scores in SQLite 
A lightweight, local database ensures quick and efficient storage.

## Outputs Top Scorers 
The highest scorers are printed directly to the console (STDOUT) for immediate visibility.

## REST API Access  
A Flask-based API makes scores accessible through simple web requests.

## API Endpoints

1. POST	/scores	Add a new score
2. GET	/scores/{name}	Retrieve a specific score by name
3. GET	/top-scorers	Retrieve the highest scorers, sorted alphabetically
 
## 2. Security Measures

To keep the system secure and prevent unauthorized access, I recommend implementing the following:

1. JWT Authentication → Users should log in with a secure token before modifying or viewing scores.
2. API Key Protection → Limit access by requiring API keys for external applications.
3. Rate Limiting → Prevent abuse by limiting the number of requests per second.
4. Data Encryption → Ensure all API communications occur over HTTPS to protect sensitive data.
5. SQL Injection Protection → Validate all inputs before inserting them into the database.

## 3. Cloud Deployment Plan

To ensure reliability and scalability, I propose two deployment options:
## Option 1: Google Cloud

1. Google Cloud Run → Fully managed and auto-scalable hosting for the Flask API.
2. Cloud SQL (PostgreSQL) → A managed database to store test scores securely.
3. Firebase Authentication → Adds secure user login and API protection.

## Option 2: AWS (Best for Larger-Scale Deployments, not necessary in our case now)

1. AWS Lambda + API Gateway → Serverless deployment for high scalability.
2. Amazon RDS (PostgreSQL) → A fully managed database solution.
3. AWS Cognito → Secure authentication and user management.
4. AWS WAF → Protects against web attacks like SQL injection and DDoS.

Both options ensure the system runs smoothly, securely, and can scale as needed.
