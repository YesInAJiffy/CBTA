# Settlement Cycle - Auth/Clearing/Settlement

To understand the **Settlement Cycle**, you have to distinguish it from the **Authorization** you see at the register. While Authorization happens in seconds, Settlement is the slower, behind-the-scenes process of actually moving the money and taking a cut for fees.

In 2026, the cycle follows three distinct phases: **Authorization**, **Clearing**, and **Settlement**.

---

### 1. Phase 1: Authorization (The "Hold")

When you tap your card, the Issuer (your bank) places a **"pending hold"** on your funds.

* **The Goal:** To prove you have the money/credit.
* **The Reality:** No money has moved yet. The merchant just has a "promise" from your bank.

### 2. Phase 2: Clearing (The "Handshake")

At the end of the business day, the merchant "batches" all their successful authorizations and sends them to their bank (the Acquirer).

* **Verification:** The Acquirer sends these details through the **Card Network** (Visa/Mastercard) to your bank.
* **Accounting:** The banks calculate exactly how much is owed, including the **Interchange Fees** we discussed. They agree on the final "net" amount to be moved.

### 3. Phase 3: Settlement (The "Payday")

This is the final stage where the actual **transfer of funds** happens.

* **The Flow:** Your bank (Issuer) sends the money to the Card Network, which then sends it to the Merchant’s bank (Acquirer).
* **The Payout:** The Acquirer deposits the money into the Merchant’s account, minus the processing fees.

---

### Settlement Timelines (The "T+" System)

The speed at which a merchant gets paid is described as **T + [Number of Days]**, where "T" is the Transaction Date.

| Cycle Type | Timeframe | Description |
| --- | --- | --- |
| **Real-Time (RTGS)** | **Instant** | Used by systems like **FedNow** or **RTP**. Settlement happens immediately with clearing. |
| **Standard (T+2)** | **2 Business Days** | The most common for 2026. If you buy a shirt on Monday, the store gets the money on Wednesday. |
| **Next-Day (T+1)** | **1 Business Day** | Premium service for merchants who want faster cash flow. |
| **Delayed (T+3+)** | **3+ Days** | Common for high-risk industries (like travel or gambling) where the bank wants to ensure no immediate chargebacks occur. |

---

### Why is there a delay?

You might wonder why, in 2026, it still takes 2 days to move digital money.

1. **Batching:** It is cheaper and more efficient for banks to move $1,000,000 once at the end of the day than to move $10 a hundred thousand times.
2. **Fraud Check:** The 24–48 hour window allows "risk engines" to flag suspicious patterns before the money is permanently gone.
3. **Netting:** If Bank A owes Bank B $1M, and Bank B owes Bank A $900k, they only settle the **$100k difference**. This requires waiting for all transactions in a day to be counted.

### The "Weekend" Rule

One thing that hasn't changed in 2026: **Standard settlement does not happen on weekends or bank holidays.**

* A transaction on **Friday** will typically not settle until **Tuesday** (T+2 business days).

**Would you like me to explain how a "Chargeback" reverses this entire settlement cycle if a customer disputes a charge?**
