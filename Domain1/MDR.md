# Merchant MDR Calculations

The **Merchant Discount Rate (MDR)** is the "all-in" fee a business pays to accept a card payment. While a merchant might see it as a single line item on their monthly statement (e.g., 2.5%), it is actually the sum of several distinct "ingredients."

As of February 2026, the calculation generally follows this additive formula:

---

### 1. The Three Components of the Calculation

To calculate the specific MDR for a single transaction, you must break it down by the entities that take a cut:

* **Interchange Fee ( of total):** This is the cost paid to the **customer's bank (the Issuer)**. It is determined by the card type (Rewards vs. Debit) and the industry (MCC).
* **Assessment Fee ( of total):** This is the fixed fee paid to the **Card Network** (Visa, Mastercard, etc.). In 2026, these are generally around **0.13% to 0.15%**.
* **Processor Markup ( of total):** This is the only **negotiable** part. It is the fee paid to the company providing the terminal and software (e.g., Square, Stripe, or a traditional bank).

---

### 2. Example Calculation (The "Coffee Shop" Scenario)

Imagine a customer buys a **$10.00** latte at your cafe using a **Mastercard Rewards Credit Card**.

| Component | Rate Logic | Calculation | Fee Amount |
| --- | --- | --- | --- |
| **Interchange** | 1.65% + $0.10 |  | **$0.265** |
| **Assessment** | 0.14% |  | **$0.014** |
| **Markup** | 0.20% + $0.05 |  | **$0.070** |
| **Total MDR** | **Sum of above** | **$0.265 + $0.014 + $0.070** | **$0.349** |

**Effective MDR:** In this case, you paid roughly **3.5%** to process that $10.00 order.

---

### 3. How Different Pricing Models Change the Math

How you "see" the calculation depends on your contract with your processor:

* **Interchange-Plus:** You see the math exactly like the table above. It is the most transparent.
* **Flat Rate (e.g., Square):** The processor does the math behind the scenes and charges you a simple **2.6% + $0.10**. If the actual interchange is low (like on a debit card), the processor keeps the extra profit. If the interchange is high (like on an Amex Platinum), the processor might actually lose money on that specific swipe.
* **Tiered Pricing:** The processor groups transactions into "Qualified" (cheapest) or "Non-Qualified" (most expensive). This is usually the least transparent way to calculate MDR.

---

### 4. Why the Calculation Varies in 2026

Your total MDR will fluctuate based on several variables:

1. **Ticket Size:** Because of the "fixed" part of the fee (the $0.10 or $0.30 per swipe), small transactions have a much higher **percentage-based** MDR than large ones.
2. **Risk Profile:** Online (Card-Not-Present) transactions always have a higher MDR calculation than in-person taps because the risk of fraud is mathematically higher.
3. **The "Durbin" Effect:** If a customer uses a **Regulated Debit Card**, your MDR calculation drops significantly because the interchange is capped at roughly **0.05% + $0.22**.




