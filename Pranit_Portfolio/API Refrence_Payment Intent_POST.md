# Create a Payment Intent

The **Payment Intent** is the primary resource used to manage the lifecycle of a card transaction. It tracks the payment from initiation through authentication and final capture. Use this endpoint to provide transaction details, such as amount and currency, to the payment gateway.


**Base URL**: https://api.paymentservice.com/v1

**Endpoint** : /payments

**Method:** POST 

**URL:** `https://sandbox-api.paymentservice.com/v1/payments`

### Authentication
Requests are authenticated using a Bearer token in the HTTP header.
`Authorization: Bearer <YOUR_SECRET_KEY>`

### Request Parameters

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `amount` | **Integer** | **Yes** | A positive integer representing the charge amount in the smallest currency unit (e.g., **100** for **$1.00**). |
| `currency` | **String** | **Yes** | 3-letter [ISO currency code](https://www.iso.org/iso-4217-currency-codes.html) in lowercase (e.g., `usd`, `eur`). |
| `payment_method` | **String** | **Yes** | The ID of the Payment Method (e.g., `pm_123...`) obtained from the client-side handoff. |
| `description` | **String** | No | An optional string describing the transaction for internal records (max 255 characters). |

---

### Sample Request



```json
{
  "amount": 2500,
  "currency": "usd",
  "payment_method": "pm_card_visa",
  "description": "Order #9876 - Wireless Headphones"
}