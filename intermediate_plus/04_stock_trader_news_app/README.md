# Stock News SMS Alert (API + Twilio)

A Python **automation script** that monitors stock price movements and sends **breaking news alerts via SMS** when a significant change occurs.  
Powered by **Alpha Vantage**, **NewsAPI**, and **Twilio**, this project keeps you informed in real time.

---

## Table of Contents

- [Preview](#preview)
- [Features](#features)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Configuration](#configuration)
- [How it works](#how-it-wors)
- [Program Flow Overview](#program-flow-overview)
- [API Usage](#api-usage)
- [Customization](#customization)
- [Security Notes](#security-notes)
- [Credits](#credits)

---

## Preview

- Monitors daily stock prices (default: **TSLA**)
- Calculates percentage change between the last two trading days
- Triggers alerts only if a configurable threshold is exceeded
- Fetches the **top 3 related news articles**
- Sends formatted SMS messages directly to your phone

---

## Features

- Real-time stock price monitoring
- Percentage-based alert threshold
- Automatic news lookup for context
- SMS delivery via Twilio
- Emoji-enhanced alerts (📈 / 📉)
- Environment-variable–based configuration
- Robust API error handling

---

## Requirements

- Python **3.x**
- `requests`
- `python-dotenv`
- `twilio`

An active internet connection is required.

---

## How to Run

1. Clone the repository:
```
git clone <repo-url>
cd <repo-folder>
```
2. Install dependencies:
```
pip install requests python-dotenv twilio
```
3. Create a `.env` file in the project root:
```
STOCK_API_KEY=your_alpha_vantage_key
NEWS_API_KEY=your_newsapi_key
TWILIO_ACCOUNT_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_token
MY_PHONE_NUMBER=+123456789
TWILIO_NUMBER=+198765432
```
4. Run:
```
python3 main.py
```
---

## Configuration

Key configuration options inside the script:

```
STOCK = "TSLA"
THRESHOLD_CHANGE = 1.0  # percent
```
- `STOCK` — ticker symbol to monitor
- `THRESHOLD_CHANGE` — minimum percentage change required to trigger alerts

---

## How it works

- The script checks the last two available trading days
- Percentage change is calculated:
  - `(latest_close - previous_close) / previous_close * 100`
- If the absolute change exceeds the threshold:
  - Fetch top 3 news articles
  - Send one SMS per article
- If not:
  - Script exits with a status message

---

## Program Flow Overview

1. Load environment variables
2. Validate required API credentials
3. Fetch daily stock prices from Alpha Vantage
4. Calculate percentage price movement
5. Check against alert threshold
6. If triggered:
  - Fetch related news articles
  - Format alert messages
  - Send SMS messages via Twilio
7. Otherwise:
  - Exit gracefully

---

## API Usage

### Stock Prices
  - Alpha Vantage
    - `https://www.alphavantage.co/query`
  - Function used
    - `TIME_SERIES_DAILY`
### News
  - NewsAPI
    - `https://newsapi.org/v2/everything`
### Messaging
  - Twilio SMS API

---

## Customization

You can extend the project easily:
- Monitor multiple stocks
- Add market open/close checks
- Schedule execution via `cron`
- Send email alerts in addition to SMS
- Include more advanced analytics (moving averages, trends)
- Store historical alerts in a database

## Security notes

- Never commit your `.env` file
- Use app-specific API keys where possible
- Twilio credentials grant real SMS-sending power — protect them
- The script validates missing environment variables before running

---

## Credits

Stock alert automation built with Python, Alpha Vantage, NewsAPI, and Twilio.
