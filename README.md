# Retail Sales Forecasting and Demand Planning with an AI Business Chat Assistant

## Project Overview
This project combines **data analytics, demand forecasting, and an AI-style business question assistant** for retail decision-making.

The system:
1. Cleans and explores retail transaction data.
2. Creates sales, revenue, product, and customer KPIs.
3. Builds a daily demand/revenue forecasting model.
4. Produces a 30-day forecast with a confidence-style prediction interval.
5. Identifies high-value products/customers and demand patterns.
6. Provides a natural-language business chat assistant that maps questions to analytical functions and returns data-driven answers.
7. Produces practical demand-planning recommendations.

## Dataset
Primary public dataset used/compatible with the notebook:

**UCI Online Retail Dataset**  
https://archive.ics.uci.edu/dataset/352/online+retail

The notebook attempts to download the dataset automatically. If the environment has no internet access, it creates a realistic synthetic retail dataset automatically so the complete workflow can still be demonstrated.

Dataset fields include invoice number, product description, quantity, invoice date, unit price, customer ID and country.

## Project Files
- `Yash_RetailSalesForecasting.ipynb` — complete analysis, forecasting model and AI assistant.
- `requirements.txt` — Python dependencies.
- `Yash_RetailSalesForecasting_ProjectReport.docx` — project documentation.
- `README.md` — project overview and setup instructions.

## How to Run
### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Open the notebook
```bash
jupyter notebook Yash_RetailSalesForecasting.ipynb
```

Run all cells from top to bottom.

## Forecasting Approach
The project aggregates transaction data to daily revenue/demand and creates:
- lag 1, 7 and 14 day features
- rolling 7 and 14 day averages
- day-of-week and month features
- trend/time index

A tree-based regression model is trained using a chronological train/test split. This avoids random shuffling and better reflects a real forecasting task.

The notebook reports MAE, RMSE and MAPE on the holdout period.

## AI Business Chat Assistant
The assistant is designed for questions such as:
- "What were total sales?"
- "Which products are performing best?"
- "What is the average daily demand?"
- "What is the forecast for the next 7 days?"
- "Which countries generate the most revenue?"
- "What should I stock more of?"
- "What was the sales trend?"

It uses TF-IDF + cosine similarity to classify the business intent and then calls the appropriate analytics function. This keeps the project runnable without an external API key.

An optional OpenAI/LLM extension can be added later, but it is not required for the submitted project.

## Business Value
The solution can support:
- inventory replenishment
- demand planning
- sales monitoring
- product prioritisation
- customer segmentation
- management reporting
- quick business-question answering

## Suggested GitHub Repository
Repository name:
`retail-sales-forecasting-ai`

Recommended structure:
```text
retail-sales-forecasting-ai/
├── Yash_RetailSalesForecasting.ipynb
├── requirements.txt
├── README.md
└── Yash_RetailSalesForecasting_ProjectReport.docx
```

## Author
Yash — MSc Food Science / Data Analytics Internship Project
AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026 | BharatCares
