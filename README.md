Markdown

# MQL5 AI Copilot & Quant Analytics 📈🤖

An intelligent, web-based quantitative trading assistant that translates natural language trading logic into robust MQL5 custom indicators, complete with an advanced backtesting and data mining dashboard.

## 🌟 Features
* **Natural Language to MQL5:** Simply describe your trading logic, and the AI generates optimized, syntax-perfect code for MetaTrader 5.
* **Quant Performance Dashboard:** Upload MT5 signal CSV files directly into the browser to extract and analyze backtest data instantly.
* **Advanced Financial Metrics:** Automatically calculates Win Rate, Total Trades, Net PnL, Profit Factor, and Max Drawdown.
* **Interactive Data Visualization:** Renders dynamic Doughnut charts (Win/Loss ratio) and Line charts (Cumulative Equity Curve) using Chart.js.
* **AI Risk Manager:** Generates structured, color-coded, and highly professional quantitative reviews of your strategy's performance to suggest actionable improvements.
* **Decoupled Architecture:** Clean separation between the client-side frontend, JS-based data mining engine, and the n8n automated backend.

## 🏗️ Architecture & Tech Stack
* **Frontend:** Vanilla HTML5, CSS3, JavaScript (Asynchronous Fetch API, Regex CSV Parser)
* **Data Visualization:** Chart.js (CDN)
* **Backend Orchestration:** [n8n](https://n8n.io/) (Node.js runtime)
* **AI Engine:** Google Gemini API (via `@n8n/n8n-nodes-langchain`)
* **Communication:** RESTful Webhooks with optimized CORS handling

## ⚙️ Prerequisites
Before running this project, ensure you have the following installed:
* [Node.js and npm](https://nodejs.org/) (for running n8n locally)
* A valid Google Gemini API Key
* Python (optional, for local web serving) or VS Code with the Live Server extension

## 🚀 Installation & Setup

### 1. Backend Setup (n8n)
1. Install n8n globally via npm:
   ```bash
   npm install -g n8n

    Start the n8n server:
    Bash

    n8n start

    Open your n8n dashboard in the browser (usually http://localhost:5678).

    Create a new workflow and build the LangChain architecture (Webhook -> AI Agent -> Window Buffer Memory & Google Gemini Model).

    Add your Google Gemini API key to the credentials section.

    Ensure the Webhook node is configured to listen to POST requests on the mql5-bot path and CORS is enabled (Respond to OPTIONS).

    Click Publish (or set to Active) to enable the Production webhook.

2. Frontend Setup

    Clone this repository or download the index.html file.

    Open index.html and ensure the webhookUrl points to your active n8n production webhook:
    JavaScript

    const webhookUrl = 'http://localhost:5678/webhook/mql5-bot';

    Crucial Step: Do not open the HTML file directly (file:///). Serve it using a local web server. Using Python:
    Bash

    python -m http.server 8000

    Open http://localhost:8000 in your web browser.

📖 How to Deploy & Analyze Data

    Click the Copy code button on the generated script in the web app.

    Open MetaTrader 5 and press F4 to launch the MetaEditor.

    Click New > Custom Indicator, delete the default code, and paste your new script.

    Press F7 to compile.

    Drag the indicator onto an active MT5 chart to auto-generate your trading signals.

    Locate the Data: In MetaEditor, go to the top menu File > Open Common Data Folder. Then navigate to the Files folder to find your generated .csv log.

    Open the Quant Dashboard in the web app, upload this CSV file, and click Generate AI Risk & Performance Review!

🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page if you want to contribute.
📄 License

This project is licensed under the MIT License.
