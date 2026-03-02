# ChatDB 21 🧠📊

**AI-Powered Natural Language Interface for Financial Markets & Investment Analysis**

ChatDB 21 enables users to interact with complex financial and sentiment data using plain English queries. It converts natural language into SQL or MongoDB queries, pulls the data from structured (MySQL) and unstructured (MongoDB) databases, and visualizes the result in an intuitive format.

---

## 📌 Features

- 💬 Natural language query interface (powered by GPT-4)
- 🗃️ Dual DB support: MySQL (market data) + MongoDB (news/sentiment)
- 📊 Interactive data visualizations
- 🔌 Real-time data fetching via Alpha Vantage API
- 🌐 Clean frontend built using Streamlit

---

## 🧰 Prerequisites

Before running the project, ensure you have the following installed:

### 🔧 Required Software

- Python 3.8+
- Git
- MySQL Server (local host: 3306)
- MongoDB Server (running locally on localhost:27017)

### 🔑 API Key
You must have an **OpenAI API key** (preferably with GPT-4 access).

Replace the API key placeholder in the script:
```python  
openai.api_key = 'sk-proj-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
```

## 🚀 Setup Instructions

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/chatdb21.git
cd chatdb21
```

### Step 2: Create a Virtual Environment (Recommended)
```bash
# For Windows
python -m venv venv
venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Required Packages
```bash
pip install -r requirements.txt
```

### Step 4: Database Setup

#### MySQL Setup
1. Ensure your MySQL server is running
2. Create the market data database:
```sql
CREATE DATABASE market_data;
```
3. Update the MySQL connection details in the app configuration if needed:
```python
# In app.py or config.py
mysql_config = {
    'host': 'localhost',
    'user': 'your_username',
    'password': 'your_password',
    'database': 'market_data'
}
```

#### MongoDB Setup
1. Ensure your MongoDB server is running on the default port (27017)
2. The application will automatically create collections as needed

### Step 5: Configure API Key
Create a `.env` file in the project root:
```
OPENAI_API_KEY=sk-proj-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

### Step 6: Run the Application
```bash
streamlit run app.py
```
The app should now be accessible at `http://localhost:8501` in your web browser.

## 📁 File Structure

This repository is organized as follows:

- **mongo_data/**: Contains MongoDB collection data and related files
  
- **mysql_data/**: Contains MySQL database dumps and structured market data files

- **.DS_Store**: macOS system file (can be ignored)

- **README.md**: This documentation file

- **requirements.txt**: List of Python package dependencies required by the application

- **streamlit_app.py**: The main application file containing the Streamlit UI and database interaction logic

```
chatdb21/
├── mongo_data/         # MongoDB collection files
├── mysql_data/         # MySQL database files
├── .DS_Store           # macOS system file (can be ignored)
├── README.md           # Documentation
├── requirements.txt    # Python dependencies
└── streamlit_app.py    # Main application
```

## 🔧 Troubleshooting

- **Database Connection Issues**: Verify your database credentials and ensure both database servers are running
- **API Key Errors**: Check that your OpenAI API key is valid and has sufficient credits
- **Package Import Errors**: Make sure all dependencies are installed with `pip install -r requirements.txt`
