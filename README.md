🚀Overview

This workflow allows a support chatbot to instantly retrieve order information from Shopify using only an order number. It replaces a slow or inconsistent manual lookup process and avoids delays. and returns a clean, human‑readable response containing:
🛍️Item names
💵Total price
📦Order status (fulfilled / in progress / unknown)
❌Clear error messages when the ID is invalid or no order is found
Everything is formatted as raw text, ready for direct chatbot replies.

🤖When the Chatbot Should Trigger This Workflow?

Your chatbot calls the workflow when:
A customer asks “Where is my order?”
A user provides an order number (e.g. 1001)
A support agent wants quick order verification without logging into Shopify
The chatbot sends a simple POST request containing:

{
  "orderId": "1001"
}

🔧How the Workflow Operates?

Secure Webhook Trigger
Accepts POST requests
Protected with basic authentication

🧹Input Validation

Rejects missing or invalid IDs
Returns a friendly error message
Fetches All Shopify Orders
Uses Get Many Orders for consistency and reliability
Filters For the Matching Order
Handles “#1001” formatting issues automatically

✍️Formats the Final Output:

Sends Clean Text Back to Webhook Caller

Sample Output
✅If the order exists
Item Names: Wireless Headphones, Xbox Wireless Gaming Controller – Carbon Black, Price: 1164.00, Status: fulfilled

❌If no order matches
Order not found. Please check the Order ID.

❗Invalid input
Invalid Order ID. Please enter a valid order number.

🔒Data Security Measures:

🔐Basic authentication on Webhook
🧽Strict input validation to block malformed requests
🚫No personal customer information shared only order basics
🔏Shopify credentials stored securely in n8n
📉No logs containing sensitive raw webhooks

🎯Summary

This automation gives support agents and chatbots a fast, reliable way to check Shopify orders without navigating the dashboard. It reduces delays, prevents manual lookup errors, and improves customer response time.
