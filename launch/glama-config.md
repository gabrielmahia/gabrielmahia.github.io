# Glama Admin Page — mpesa-mcp Dockerfile Configuration
# URL: https://glama.ai/mcp/servers/mpesa-mcp (or search for it)
# Go to: Admin → Docker Configuration

# === FILL IN THIS FORM DATA ===

Build steps (one per line):
pip install mpesa-mcp==0.1.9

CMD:
mpesa-mcp

# === ENVIRONMENT VARIABLES (placeholder values for sandbox) ===
MPESA_CONSUMER_KEY: (user's key from developer.safaricom.co.ke)
MPESA_CONSUMER_SECRET: (user's secret)
MPESA_SHORTCODE: 174379
MPESA_PASSKEY: bfb279f9aa9bdbcf158e97dd71a467cd2e0c893059b10f78e6b72ada1ed2c919
MPESA_ENV: sandbox
MPESA_CALLBACK_URL: https://your-callback-url.com/mpesa/callback

# === DESCRIPTION FOR GLAMA ===
MCP server for M-PESA Daraja API — Kenya's dominant mobile money platform.
Enables AI agents to initiate STK push payments, check balances, query 
transaction status, and register C2B callback URLs. First East African 
payment API in the MCP ecosystem.

Tools:
- mpesa_stk_push: Initiate Lipa Na M-PESA payment
- mpesa_b2c: Business-to-customer disbursement  
- mpesa_balance: Account balance query
- mpesa_transaction_status: Transaction status check
- mpesa_register_url: C2B URL registration

Sandbox credentials: developer.safaricom.co.ke (free registration)
