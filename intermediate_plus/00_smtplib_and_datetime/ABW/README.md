# Automated Birthday Email Sender

A small **automation script** that sends personalized birthday emails automatically using **Python**, **Pandas**, and **SMTP**.  
Each day, the script checks a CSV file for birthdays and sends a randomly selected congratulatory email to matching recipients.

---

## Table of Contents

- [Preview](#preview)
- [Features](#features)
- [Requirements](#requirements)
- [How to Run](#how-to-run)
- [Configuration](#configuration)
- [Program Flow Overview](#program-flow-overview)
- [Customization](#customization)
- [Security Notes](#security-notes)
- [Credits](#credits)

---

## Preview

- Automatically checks **today’s date**
- Matches birthdays stored in a CSV file
- Selects a **random email template**
- Personalizes the message using the recipient’s name
- Sends the email via **SMTP (Gmail or Yahoo)**

---

## Features

- Daily birthday matching using real date/time
- CSV-driven data source (easy to extend)
- Randomized email templates
- Personalized email content (`[NAME]` placeholder)
- Supports multiple email providers
- Uses environment variables for credentials (secure)

---

## Requirements

- Python **3.x**
- `pandas`
- `python-dotenv`

Standard library modules used:
- `datetime`
- `random`
- `os`
- `smtplib`

---

## How to Run

1. Clone the repository:
```
git clone <repo-url>
cd <repo-folder>
```
2. Install dependencies
```
pip install pandas python-dotenv
```
3. Create a `.env` file:
```
SMTP_EMAIL=your_email@example.com
SMTP_PASSWORD=your_app_password
```
4. Run script
```
python3 main.py
```
---

## Configuration

### `birthdays.csv`

Must contain the following columns:

| Column | Description |
|------|-------------|
| name | Recipient name |
| email | Recipient email |
| year | Birth year |
| month | Birth month |
| day | Birth day |

---

## How it works

- The script checks today’s `(month, day)`
- If a matching birthday exists:
  - A random letter template is selected
  - `[NAME]` is replaced with the recipient’s name
  - An email is sent automatically
- If no birthday matches:
  - The script exits silently

---

## Program Flow Overview

1. Load current date
2. Read birthday data into a DataFrame
3. Build a lookup dictionary `(month, day) → person`
4. Check for today’s date
5. Select a random letter template
6. Personalize the message
7. Detect mail provider (Gmail / Yahoo)
8. Load SMTP credentials from `.env`
9. Send the email securely via TLS

---

## Customization

You can easily extend this project:

- Add more recipients to `birthdays.csv`
- Add more templates to `letter_templates/`
- Schedule with `cron` or Windows Task Scheduler
- Add support for more email providers
- Send emails to multiple people on the same day
- Log sent emails to a file

---

## Security Notes

- Never commit your `.env` file
- Use **App Passwords** for Gmail/Yahoo
- Credentials are loaded securely via environment variables
- TLS encryption is enabled (`starttls()`)

---

## Credits

Automated birthday email sender built with Python, Pandas, and SMTP.
