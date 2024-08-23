Grade Recording System with XRPL
Overview
The Grade Recording System with XRPL is a web-based application that utilizes blockchain technology to securely and transparently record academic grades. This system leverages the XRP Ledger (XRPL) for storing and managing academic records, ensuring data integrity and immutability. This project uses Express.js for the backend, integrating the XRPL for blockchain functionality.

Features
Blockchain-Based Grade Storage: Securely stores student grade records on the XRPL, ensuring immutability.
Record History: Maintains a history of all grade records stored during the application's runtime.
Web Interface: Provides a simple web interface for interacting with the system.
Unique Record Identification: Uses unique identifiers for each record to ensure traceability.

Prerequisites
Node.js and npm installed on your system.
Internet connection to connect to the XRPL testnet.
Setup and Installation
Clone the Repository:

bash
Copy code
git@gitlab.com:xrpl2/student_grading.git
cd grade-recording-system-xrpl
Install Dependencies:

bash
Copy code
npm install
Run the Application:

bash
Copy code
node app.js
Access the Web Interface:

Open your web browser and navigate to http://localhost:3000 to access the Grade Recording System.

Code Structure
Express Setup: The application uses Express.js to set up a simple server. It listens on port 3000 and serves the static files required for the frontend.

Routes:
GET /frontend.js: Serves the frontend JavaScript file for the application.
GET /history: Returns the record history as JSON.
POST /create-record: Accepts a JSON payload to create a new grade record, stores it in memory, and interacts with the XRPL.
Record History: Stores all records in an array during the application's runtime. In a real application, this would be replaced by a database for persistent storage.
Ripple (XRP) Ledger Integration: The application connects to the XRPL testnet to interact with the blockchain. Ensure the testnet connection URL is correct and the Ripple client is initialized properly.
Usage
Access the Application:
Open the web browser and go to http://localhost:3000.
Create a Record:
Send a POST request to /create-record with the required data: studentId, name, course, grade, year, and rippleAddress.

Example payload:
json
Copy code
{
  "studentId": "12345",
  "name": "John Doe",
  "course": "Blockchain 101",
  "grade": "A",
  "year": "2024",
  "rippleAddress": "rPT1Sjq2YGrBMTttX4GZHjKu9dyfzbpAYe"
}

View Record History:
Send a GET request to /history to retrieve all stored records.
Functions
generateRandomId(): Generates a random ID for each record. This can be replaced with a more robust ID generation mechanism as needed.

Important Notes
This project currently uses an in-memory array (recordHistory) to store records. In a production environment, consider using a database like MongoDB or MySQL for persistent storage.
The Ripple integration is set to use the testnet (wss://s.altnet.rippletest.net:51233). Ensure to switch to the mainnet for production use and handle credentials securely.

Error Handling
If the provided data is incomplete or incorrect, the server responds with a 400 status code and an error message.
In case of a failure in connecting to the XRPL or processing the transaction, the server responds with a 500 status code and the error message.

Conclusion
This Grade Recording System with XRPL project demonstrates the integration of blockchain technology with academic record-keeping. It provides a secure, transparent, and efficient way to manage student grades using the XRP Ledger.
