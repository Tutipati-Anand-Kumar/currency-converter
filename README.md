# 🌍 StellarSwap: Modern Currency Converter

A stylish, responsive, and feature-rich currency converter application built with vanilla JavaScript, Bootstrap 5, and Font Awesome. It provides real-time (or mocked) exchange rate lookups with a dynamic, user-friendly interface.

---

## ✨ Features

* **Responsive Design:** Utilizes **Bootstrap 5** for a clean, mobile-friendly interface.
* **Live Currency Search:** Interactive search dropdowns for selecting source and target currencies by code or name.
* **Swap Functionality:** A dedicated button to quickly swap the source and target currencies.
* **Live Exchange Rate Fetching:** Integration with an external API for up-to-date conversion rates (with a fallback to mock data).
* **Dynamic Results:** Visually appealing success section for displaying the converted amount and the current exchange rate.
* **Input Validation & Error Handling:** Ensures valid amounts are entered and displays clear error messages for failed API calls.
* **Visual Flair:** Custom CSS styling, gradient effects, button animations, loading state, and a **confetti 🎉** effect on successful conversion.

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | HTML5, CSS3, Vanilla JavaScript (ES6+) | Core structure and logic. |
| **Styling** | **Bootstrap 5** | Responsive layout and utility classes. |
| **Icons** | **Font Awesome 6.4.0** | Professional icons for controls and labels. |
| **API** | **ExchangeRate-API (v6)** | Used for fetching up-to-date exchange rates. |

---

## 🔑 API Used & Configuration

This converter is primarily configured to use the **ExchangeRate-API** to fetch the conversion rate between two specific currencies.

### API Details

* **Service:** ExchangeRate-API (v6)
* **Endpoint:** `https://v6.exchangerate-api.com/v6/{API_KEY}/pair/{SOURCE_CURRENCY}/{TARGET_CURRENCY}`
* **Key Location:** The API key is stored in the `exchangeRateApiKey` variable within the `CurrencyConverter` class's constructor:

    ```javascript
    class CurrencyConverter {
        constructor() {
            // Your API Key
            this.exchangeRateApiKey = 'b2e825bd5d39e98771b08213'; 
            this.exchangeRateApiBaseUrl = `https://v6.exchangerate-api.com/v6/${this.exchangeRateApiKey}/pair/`;
            // ... rest of the constructor
        }
        // ...
    }
    ```

### Fallback Mechanism (Mock Data)

A robust fallback mechanism is implemented via the `getMockExchangeRate` method.

* If the primary API call to `ExchangeRate-API` fails (e.g., due to an error, rate limit, or network issue), the application gracefully falls back to a predefined set of **mock rates** for major currencies (USD, EUR, GBP, INR, JPY, AUD, CAD, CNY) and calculates the conversion using this mock data.

---

## 🚀 Getting Started

Follow these steps to set up and run the project locally.

### Prerequisites

1.  A modern web browser (Chrome, Firefox, Edge, Safari).
2.  A valid **API Key** from a service like **ExchangeRate-API** (you can sign up for a free plan).

### Steps to Follow

1.  **Save the Code:** Save the entire provided HTML content into a file named `index.html`.

2.  **Obtain an API Key (Optional but Recommended):**
    * Go to a currency exchange rate API provider (e.g., [ExchangeRate-API](https://www.exchangerate-api.com/) or [FastForex](https://www.fastforex.io/)).
    * Sign up and obtain your unique API key.

3.  **Update the API Key:**
    * Open `index.html`.
    * Search for the `CurrencyConverter` class's constructor.
    * Replace the placeholder value for `this.exchangeRateApiKey` with your actual key.

    ```javascript
    // Inside the <script> tag:
    this.exchangeRateApiKey = 'YOUR_ACTUAL_API_KEY_HERE'; 
    ```
    *(Note: The provided key `b2e825bd5d39e98771b08213` may be expired or invalid. Replacing it with a new key is essential for live data.)*

4.  **Run the Application:**
    * Simply **double-click** the `index.html` file in your local file system. It will open directly in your web browser.

5.  **Use the Converter:**
    * Enter an **Amount** (default is 100).
    * Use the search boxes to select your **Source Currency** and **Target Currency**.
    * Click the **Convert** button to see the result!
