# Dialogflow Telegram Chatbot - Currency Converter

This project implements a simple **currency converter chatbot** using **Dialogflow** and **Flask**. The chatbot takes user queries from Dialogflow, processes currency conversion requests, and responds with the converted amount.

---

## Features

- Accepts currency conversion queries via Dialogflow webhook.
- Retrieves real-time currency conversion rates using the [Currency Converter API](https://free.currconv.com/).
- Calculates and returns the converted amount with two decimal precision.
- Integrates easily with Telegram (or any other platform supported by Dialogflow).
- Built with Flask for lightweight, easy-to-deploy backend.

---

## Technologies Used

- **Python 3.x**
- **Flask** — Lightweight web framework to create the webhook API.
- **Dialogflow** — Natural language understanding platform to handle user queries and intent parsing.
- **Currency Converter API** — Public API to fetch currency exchange rates.
- **Requests** — Python HTTP library for API calls.

---


## How It Works

- The user sends a message (e.g., "Convert 10 USD to INR") via Telegram (or other Dialogflow integrated platform).
- Dialogflow parses the intent and extracts parameters like source currency, amount, and target currency.
- Dialogflow sends a webhook POST request to this Flask backend.
- The backend fetches the current conversion rate from the Currency Converter API.
- The backend calculates the converted amount and sends a response back to Dialogflow.
- Dialogflow replies to the user with the conversion result.

---

## Example Request Payload

```json
{
  "queryResult": {
    "parameters": {
      "unit-currency": {
        "currency": "USD",
        "amount": 10
      },
      "currency-name": "INR"
    }
  }
}
