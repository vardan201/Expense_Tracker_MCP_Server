# Expense Tracker MCP Server 💰

An **Expense Tracking MCP (Model Context Protocol) Server** built using **FastMCP**, **async SQLite (aiosqlite)**, and **HTTP transport**.  
This server allows AI agents or clients to **add, list, and summarize expenses** using structured MCP tools.

---

## 🚀 Features

- ✅ Add expenses asynchronously
- 📅 List expenses within a date range
- 📊 Summarize expenses by category
- 📂 Persistent SQLite database (stored in system temp directory)
- 🧠 MCP-compatible tools for AI agents
- 🌐 HTTP-based MCP server
- 🏷️ Category resource endpoint with fallback defaults

---

## 🧩 Tech Stack

- **Python 3.9+**
- **FastMCP**
- **aiosqlite**
- **SQLite (WAL mode)**
- **MCP Protocol**
- **HTTP Transport**

---

## 📁 Project Structure

Expense_Tracker_MCP_Server/
│
├── test-remote-mcp-server/
│ ├── server.py # Main MCP server
│ ├── categories.json # Optional category definitions
│ └── README.md

yaml
Copy code

---

## ⚙️ Installation

### 1️⃣ Clone the repository
```bash
git clone https://github.com/vardan201/Expense_Tracker_MCP_Server.git
cd Expense_Tracker_MCP_Server
2️⃣ Create virtual environment (recommended)
bash
Copy code
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
3️⃣ Install dependencies
bash
Copy code
pip install fastmcp aiosqlite
▶️ Running the Server
bash
Copy code
python server.py
Server will start at:

cpp
Copy code
http://0.0.0.0:8000
🗄️ Database Details
Database is created automatically

Stored in system temp directory:

pgsql
Copy code
/tmp/expenses.db   (Linux/macOS)
C:\Users\<user>\AppData\Local\Temp\expenses.db   (Windows)
Uses WAL (Write-Ahead Logging) mode

Read/write permissions are verified on startup

🛠️ MCP Tools
➕ add_expense
Add a new expense entry.

Parameters

date (string, YYYY-MM-DD)

amount (float)

category (string)

subcategory (optional)

note (optional)

📄 list_expenses
List expenses within a date range.

Parameters

start_date

end_date

📊 summarize
Summarize expenses by category.

Parameters

start_date

end_date

category (optional)

📦 MCP Resource
expense:///categories
Returns available expense categories as JSON.

Loads from categories.json if available

Falls back to default categories if missing

Example categories:

Food & Dining

Transportation

Shopping

Entertainment

Bills & Utilities

Healthcare

Travel

Education

Business

Other

🧠 Use Cases
AI-powered expense tracking

Personal finance assistants

Budgeting copilots

MCP-compatible agent backends

Learning MCP + async Python patterns

🔐 Error Handling
Graceful handling of database read-only states

Clear error messages returned via MCP tools

Safe async database operations

📌 Notes
Some parts of this project are adapted from FastMCP examples

Database initialization runs synchronously for safety

Async operations are used for all runtime queries

👤 Author
Vardan Srivastava
GitHub: https://github.com/vardan201
