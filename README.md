# Funding Project Automation 🤖

An automated workflow built with n8n that extracts structured data from promissory note PDFs via Telegram and logs it directly into Google Sheets.

## ⚙️ How It Works

1. **Telegram Trigger** — Listens for incoming messages on a Telegram bot
2. **PDF Validation** — Checks if the uploaded file is a PDF; ignores other file types
3. **File Download** — Retrieves the PDF file via Telegram's API
4. **Text Extraction** — Extracts raw text content from the PDF
5. **AI Processing** — Uses Google Gemini to parse the promissory note and extract key fields, applying a custom formula to calculate the net amount
6. **Data Parsing** — A JavaScript snippet converts the AI's JSON output into structured data
7. **Google Sheets Logging** — Appends the extracted data as a new row in the target spreadsheet

## 🛠 Tools Used

- **n8n** — Workflow automation
- **Telegram Bot API** — File receiving trigger
- **Google Gemini** — AI-powered data extraction
- **Google Sheets** — Data storage
- **JavaScript** — JSON parsing

## 📋 Extracted Fields

| Field | Description |
|-------|-------------|
| اسم العميل | Client full name |
| هوية العميل | Client ID number |
| المبلغ | Net amount after formula |
| التاريخ | Issue date (DD/MM/YYYY) |
| تاريخ الاستحقاق | Due date (DD/MM/YYYY) |
| رقم السند | Promissory note number |
| المستثمر | Investor name |
| مبلغ الاستحقاق | Final due amount |
| حالة السداد | Payment status |

## 🧮 Amount Formula

```
Net Amount = (Note Value - 500) / 1.3
```

## 🚀 Setup

1. Import `workflow_clean.json` into your n8n instance
2. Replace all placeholders with your own credentials:
   - `{YOUR_TELEGRAM_BOT_TOKEN}` — Your Telegram bot token from BotFather
   - `{YOUR_GOOGLE_SHEET_ID}` — Your Google Sheets document ID
   - `{INVESTOR_NAME}` — Investor name
   - `{SHEET_NAME}` — Your sheet name
3. Connect your Telegram and Google Sheets credentials in n8n
4. Activate the workflow

## 👤 Contact

**Muhannad Aljuraed**  
[LinkedIn](https://www.linkedin.com/in/muhannad-al-shammari-/)
