# Eldorado Node - HR Intelligence System

Marketing website for the Eldorado Node HR Intelligence SaaS platform.

Live at: https://hr.eldoradonode.work

## Pages

- `index.html` — Main landing page with pricing and checkout
- `privacy.html` - Privacy Policy (GDPR, UAE PDPL, Nigeria NDPR compliant)
- `terms.html` — Terms of Service
- `dpa.html` — Data Processing Agreement
- `CNAME` — GitHub Pages custom domain config

## Setup

### 1. GitHub Pages
- Go to repo Settings → Pages
- Source: Deploy from branch → main → / (root)
- Custom domain: hr.eldoradonode.work

### 2. DNS Records (add to your domain registrar)
Add a CNAME record:
- Type: CNAME
- Name: hr
- Value: eldoradonode.github.io
- TTL: 3600

### 3. Swap placeholders in index.html
Search for these strings and replace with real values:

| Placeholder | What to replace with |
|---|---|
| `YOUR_PAYSTACK_PUBLIC_KEY_HERE` | Your Paystack public key (pk_live_...) |
| `YOUR_STRIPE_PUBLIC_KEY_HERE` | Your Stripe public key (pk_live_...) |
| `YOUR_STRIPE_STARTER_PAYMENT_LINK` | Stripe Payment Link URL for Starter plan |
| `YOUR_STRIPE_GROWTH_PAYMENT_LINK` | Stripe Payment Link URL for Growth plan |
| `YOUR_STRIPE_ENTERPRISE_PAYMENT_LINK` | Stripe Payment Link URL for Enterprise plan |
| `YOUR_ADMIN_SECRET_HERE` | Your ADMIN_SECRET env variable value |
| `YOUR_TRC20_WALLET_ADDRESS_HERE` | Your USDT TRC-20 wallet address |
| `TYour_TRC20_Wallet_Address_Here` | Same TRC-20 wallet address (appears twice) |
| `https://hbclurvd.rpcl.app` | Your n8n instance URL |

### 4. Stripe Setup
1. Go to stripe.com → Create account
2. Go to Payment Links → Create 3 payment links (one per plan)
3. Set amounts: $149, $349, $899
4. Copy each link URL and paste into index.html
5. Set up Stripe webhook to call your Admin API on payment.success

### 5. Update USD to NGN rate
In index.html find `const USD_TO_NGN = 1650` and update to current rate before going live.

## Related Repos

- Intake form: https://github.com/eldoradonode/eldorado-intake
- Portfolio: https://eldoradonode.work
