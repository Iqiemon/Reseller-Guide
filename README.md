# Lucia Bot — Reseller Guide

Welcome to Lucia Bot. This guide covers everything you need to get started as a reseller.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Basic Commands](#basic-commands)
3. [Checking Your Balance](#checking-your-balance)
4. [Topping Up Your Balance](#topping-up-your-balance)
5. [Placing Orders](#placing-orders)
6. [Tracking Orders](#tracking-orders)
7. [Pricing & Rates](#pricing--rates)
8. [Tips & Best Practices](#tips--best-practices)
9. [FAQ](#faq)

---

## Getting Started

### How to Get Access

Access is by invitation only. To register:

1. Contact the admin on Telegram: **@lucreciaops**
2. Provide your Telegram ID (the bot will show this automatically if you try to use a command before registration)
3. The admin will activate your account
4. You'll receive a confirmation message once registered

> **Note:** Your Telegram ID is a number (e.g., `123456789`), not your username.

### First Steps After Registration

```
/start        — See the welcome message
/commands     — View all available commands
/info         — Check your Telegram ID and current balance
```

---

## Basic Commands

| Command | Description |
|---------|-------------|
| `/start` | Welcome message |
| `/commands` | List all commands |
| `/info` | Your Telegram ID and balance |
| `/games` | List all available games |
| `/game <game_code>` | Show order format for a game |
| `/rates <game>` | See prices for a game |
| `/check <game> <userid> [serverid]` | Verify an account before ordering |
| `/track <order_id>` | Check the status of an order |
| `/orders` | List all available order methods |
| `/deposit_myr <amount>` | Deposit MYR via online banking |
| `/deposit_usdt <amount>` | Deposit via USDT |

---

## Checking Your Balance

```
/info
```

This shows your current Telegram ID and available balance in MYR.

---

## Topping Up Your Balance

There are two ways to add funds to your account.

---

### Option 1: FPX Online Banking (MYR)

```
/deposit_myr <amount>
```

**Example:**
```
/deposit_myr 100
```

- Minimum: **RM10**
- Maximum: **RM500** per deposit
- Daily limit: **RM500**
- Amount must be a **whole number** (no decimals)
- Processing fee: ~RM1.10 (charged by payment gateway)
- Expires in **60 minutes**

**Steps:**
1. Run `/deposit_myr 100`
2. Bot shows the amount, processing fee, and total charge
3. Click **"Pay Now"** to open the FPX payment page
4. Complete payment via your online banking
5. Balance is credited automatically once confirmed (usually within a few minutes)

---

### Option 2: USDT (Crypto)

```
/deposit_usdt <amount>
```

**Example:**
```
/deposit_usdt 50
```

- Minimum: **1 USDT**
- Maximum: **10,000 USDT** per deposit
- Expires in **60 minutes**
- Supported networks: **BEP20 (BSC)**, **TRC20 (Tron)**, **Polygon**

**Steps:**
1. Run `/deposit_usdt 50`
2. Bot shows the USDT amount, estimated MYR credit, and current exchange rate
3. Click **"Open Deposit Page"** to get your wallet address and QR codes
4. Send **exactly** the specified USDT amount to the shown address
5. Balance is credited automatically after blockchain confirmation (usually 5–15 minutes)

> **Important:** Send only from a wallet you control. Do not send from an exchange if the network fee is unpredictable. Send the exact amount shown.

---

## Placing Orders

### Step 1: Browse Available Games

```
/games          — List all games
/game mlbb   — See the order format for a specific game
/rates mlbb — See available denominations and prices
```

### Step 2: Verify the Account (Recommended)

Before ordering, verify the player's account ID is correct:

```
/check <game> <userid> [serverid]
```

**Example:**
```
/check mlbb 50224245 2214
```

The bot will confirm the player's username if the ID is valid.

---

### Step 3: Place the Order

The recommended order command is `/order`.

```
/order <game> <denom> <userid> [serverid]
```

**Example (MLBB):**
```
/order mlbb 86 50224245 2214
```

| Field | Description | Example |
|-------|-------------|---------|
| `game` | Game code (from `/games`) | `mlbb` |
| `denom` | Denomination/amount | `86` |
| `userid` | Player's in-game ID | `50224245` |
| `serverid` | Server ID (if required) | `2214` |

> Not all games require a server ID. Run `/game <game_code>` to see what fields are needed.

---

### What Happens After You Place an Order

1. The bot checks your balance
2. If sufficient, balance is **deducted immediately**
3. Order is submitted for processing
4. You receive a confirmation message with:
   - Order ID
   - Game and denomination
   - Amount charged
   - Your balance before and after
   - A **"Track Order"** button

---

### Other Order Commands

Different order commands use different processing routes. Use `/orders` to see the full list.

| Command | Use Case |
|---------|----------|
| `/order9` | **Recommended** — most games |
| `/order` | Alternative route |
| `/order3` | Alternative route |
| `/order5` | Certain games/regions |
| `/order8` | Select products only |

When in doubt, use `/order9`. Contact the admin if you need a specific route.

---

## Tracking Orders

### After Placing an Order

Click the **"Track Order"** button in the order confirmation message to check status instantly.

### Manual Tracking

```
/track <order_id>
```

**Example:**
```
/track SSa1b2c3d4e5f6g7h8
```

Your order ID starts with `SS` followed by alphanumeric characters. It is shown in the order confirmation message.

### Order Statuses

| Status | Meaning |
|--------|---------|
| ✅ **Completed** | Order delivered successfully |
| ❌ **Failed** | Order failed — refund will be processed |
| ⏳ **Processing / Pending** | Order is in progress — check again shortly |

> If an order fails, your balance will be refunded automatically. If a refund does not appear within a reasonable time, contact the admin.

---

## Pricing & Rates

### Checking Prices

```
/rates <game>         — Prices for a game (default route)
/rates9 <game>        — Prices via the recommended route
```

**Example:**
```
/rates9 mlbb_my
```

This shows all available denominations and their prices in MYR with margin included.

### How Pricing Works

- Prices shown are **final prices** — what you pay
- A margin is built into all prices
- Prices are in **MYR**
- Prices may fluctuate slightly based on exchange rates (for foreign currency games)

---

## Tips & Best Practices

1. **Always verify the account first.** Use `/check` before placing an order. Wrong account IDs cannot be refunded.

2. **Double-check the game code and server ID.** Run `/game <game_code>` to confirm the required fields.

3. **Keep your order IDs.** Save the order confirmation message in case you need to follow up.

4. **Top up in advance.** Don't wait until your balance is zero to deposit — FPX and USDT deposits require a few minutes to process.

5. **Use `/track` if unsure.** If you don't receive a result message, check the order status before re-ordering.

6. **For FPX deposits:** Complete payment within 60 minutes or the deposit request will expire.

7. **For USDT deposits:** Send the exact amount shown, on the correct network. Wrong network = funds may be lost.

---

## FAQ

**Q: How do I get my Telegram ID?**
Try running any command (e.g., `/info`) and the bot will show it if you're not registered yet.

---

**Q: My order is stuck on "Processing" — what do I do?**
Wait a few minutes — most orders complete within 1–5 minutes. If it's been more than 10 minutes, contact the admin with your order ID.

---

**Q: My order failed. Will I get a refund?**
Yes. Failed orders are automatically refunded to your balance. Check `/info` to confirm your balance.

---

**Q: Can I cancel an order?**
Orders are submitted immediately and cannot be cancelled once placed. Verify account IDs before ordering.

---

**Q: I deposited USDT but my balance hasn't updated.**
Blockchain confirmations can take 5–15 minutes. If it's been longer than 30 minutes, contact the admin with your transaction hash.

---

**Q: The FPX deposit page expired — did my money go through?**
If you completed payment before the 60-minute expiry, the balance will still be credited. Contact the admin if it doesn't appear within 30 minutes.

---

**Q: How do I know which denominations are available?**
Run `/rates9 <game>` or `/games9` to see all options with prices.

---

**Q: I get "You don't have enough balance!" but I just deposited.**
Deposits can take a few minutes to confirm. Wait a moment and try again. Run `/info` to check your current balance.

---

*For support, contact the admin on Telegram: @lucreciaops*
