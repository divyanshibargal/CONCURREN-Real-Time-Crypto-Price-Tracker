# 🪙 CONCURREN — Real-Time Crypto Price Tracker

CONCURREN is a modular Python project that fetches live cryptocurrency prices using the CoinGecko API, stores the latest snapshot in a MySQL database, and exports it to a CSV file. It auto-refreshes every minute to keep your data up-to-date.

---

## 🚀 Features

- ✅ Fetches live prices for Bitcoin, Ethereum, Solana, Dogecoin, and Cardano
- ✅ Stores latest prices in a MySQL database (overwrites old data)
- ✅ Exports latest snapshot to a CSV file (overwrites each cycle)
- ✅ Auto-refreshes every 60 seconds
- ✅ Modular structure with clean separation of concerns

---

## 🧠 Project Structure

CONCURREN/ 
├── config/ 
│ └── db_config.py # Loads DB credentials from .env 
├── data/ 
│ └── summary.csv # Optional summary output 
├── logs/ 
│ └── crypto_prices.csv # Overwritten every cycle 
├── modules/ 
│ ├── fetch_data.py # CoinGecko API integration 
│ ├── db_handler.py # MySQL insert logic 
│ └── csv_exporter.py # CSV export logic
├── scheduler/ 
│ └── auto_refresh.py # Main loop with 60s refresh 
├── .env # DB credentials (not committed) 
├── main.py # Entry point 
└── requirements.txt # Dependencies

---

## ⚙️ Setup Instructions

### 1. Clone the repo

```bash
git clone https://github.com/your-username/concurren.git
cd concurren

### 2. Create and activate virtual environment**
python3 -m venv venv
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate     # Windows

3. Install dependencies
pip install -r requirements.txt

4. Configure .env
Create a .env file in the root folder:
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=concurren

5. Run the tracker
python main.py

🧪 Output
✅ Console prints live prices every minute

✅ logs/crypto_prices.csv contains only the latest snapshot

✅ MySQL table prices is truncated and updated each cycle


📦 Dependencies
pandas
requests
python-dotenv
mysql-connector-python
These are listed in requirements.txt



