# 💰 Simple Transaction Tracker React App

A lightweight React app to track financial transactions, display a running balance, and log transaction details with date/time and descriptions.

---

## 🚀 Features

- Add new transactions with:
  - Price and name (entered together, price is extracted automatically)
  - Description
  - Date and time (using native datetime-local input)
- Display a live running balance with cents styled separately.
- List all transactions with name, description, price (color-coded for income/expense), and timestamp.
- Fetch existing transactions from a backend API on load.
- Post new transactions to backend API.

---

## 🛠 Tech Stack

- React (with hooks: useState, useEffect)
- Fetch API for backend communication
- CSS for styling (imported as `App.css`)

---

## 📂 Project Structure

src/
├── App.js # Main React component
├── App.css # Styling for the app
├── index.js # React DOM entry point

---

## 🔧 Installation & Setup

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/transaction-tracker.git
cd transaction-tracker

Install dependencies

bash
Copy
Edit
npm install
# or
yarn install
Set environment variable

Create a .env file in the root directory with your backend API URL:

ini
Copy
Edit
REACT_APP_API_URL=https://your-backend-api.com/api
Start the app

bash
Copy
Edit
npm start
# or
yarn start
Open http://localhost:3000 to view it in your browser.

📋 How It Works
On load, the app fetches transactions from GET /transactions endpoint of your API and displays them.

The balance is calculated as the sum of all transaction prices.

To add a new transaction:

Enter the price followed by the transaction name in the first input (e.g., -20 Grocery).

Add optional description and pick date/time.

On submit, a POST request is sent to /transaction endpoint with JSON body containing price, name, description, and datetime.

Transactions are displayed with:

Green text for positive prices (income).

Red text for negative prices (expenses).

Date/time shown next to price.

💡 Notes
The app expects your backend to expose these endpoints:

GET /transactions - returns list of transactions as JSON.

POST /transaction - accepts a transaction object to save.

The price is parsed from the first word of the "Transaction" input field. Be sure to input price followed by name separated by a space.
