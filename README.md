# ChronoBank ⏳💰

ChronoBank is a secure **time-based banking web application** built with Flask and PostgreSQL,  
where **time (in hours/seconds)** functions as the currency instead of money.  

Users can **deposit, withdraw, invest, and borrow time** — just like in traditional banking.  
It features **fraud detection**, **real-time transaction logging**, and applies **design patterns** for scalable architecture.

---

## ✨ Features

- **Core Banking with Time as Currency**
  - Deposit, withdraw, invest, and take loans in time units  
  - Real-time transaction updates and bonuses (e.g., *36000 seconds bonus applied*)  

- **Fraud Detection**
  - `/api/fraud-alerts` endpoint monitors suspicious activities  
  - Notifications and logging integrated into the transaction flow  

- **API-Driven Communication**
  - Flask provides REST APIs for page-to-page communication  
  - Routes like `/accounts/create`, `/accounts/{id}/deposit`, `/notifications/count`  

- **Security**
  - Session-based authentication & access control  
  - PostgreSQL-backed persistent storage  
  - Transaction logs for auditing  

## 🧩 Design Patterns Used

### Creational
- **Builder** → Step-by-step construction of complex account objects  
- **Factory** → Dynamic creation of account types (Savings, Investment, Loan)  
- **Singleton** → Ensures only one database/session manager instance  

### Structural
- **Facade** → Unified interface for multi-step operations (e.g., loan processing)  
- **Decorator** → Extend account functionality (fraud checks, bonus application)  
- **Adapter** → Bridge between different services/APIs  

### Behavioral
- **Command** → Encapsulates operations (deposit, withdraw, transfer) as objects  
- **Observer** → Notify fraud detection and notification services on transaction events  
- **Strategy** → Flexible algorithms for interest calculation, fraud detection, loan repayment 
---

## 🛠️ Tech Stack

- **Backend**: Flask (Python)  
- **Database**: PostgreSQL (SQLAlchemy ORM)  
- **Frontend**: HTML, CSS, Jinja2 templates  
- **APIs**: REST endpoints for accounts, transactions, notifications, fraud alerts   
---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+  
- PostgreSQL (running locally or remote)  

### Installation

1. **Clone repo**
```bash
git clone https://github.com/harsh-parakh22/ChronoBank.git
cd ChronoBank
```
2. **Set up virtual environment**
- python3 -m venv venv
- source venv/bin/activate    # Linux/Mac
- venv\Scripts\activate       # Windows

3.**Install dependencies**
- pip install -r requirements.txt

4.**Configure database**
 Create a PostgreSQL database:
  - CREATE DATABASE chronobank;
 Update DB URI in config.py or .env:
  - DATABASE_URL=postgresql://username:password@localhost/chronobank

5.**Initialize migrations**
  - flask db init
  - flask db migrate
  - flask db upgrade

6.**Run the app**
  - python run.py

**📡 Example Routes**

- POST /accounts/create → create account
- POST /accounts/<id>/deposit → deposit time
- GET /accounts/<id> → view account info
- GET /notifications/count → get notification count
- GET /api/fraud-alerts/count → check fraud alerts

**🏦 Core Banking Operations**

- Deposit Time → Add hours to your account balance
- Withdraw Time → Deduct hours from balance
- Invest Time → Earn interest over time deposits
- Take Loan → Borrow time with repayment schedules
- Upgrade Account → Switch between account types (handled by Factory pattern)

**🔐 Fraud Detection**

- User performs a transaction
- Command pattern executes the operation
- Observer pattern notifies fraud detection & notification systems
- Decorator pattern applies fraud-check logic before committing
- Fraud alerts recorded via /api/fraud-alerts
  
**🔐 Security**

- Session-based authentication
- Transaction logging for all account activities
- Role-based access (regular user, admin)

![IMG1](imgs/ss1.png)
![IMG1](imgs/ss2.png)
![IMG1](imgs/ss3.png)
![IMG1](imgs/ss4.png)
![IMG1](imgs/ss5.png)
![IMG1](imgs/ss6.png)
![IMG1](imgs/ss7.png)
![IMG1](imgs/ss8.png)
![IMG1](imgs/ss9.png)
