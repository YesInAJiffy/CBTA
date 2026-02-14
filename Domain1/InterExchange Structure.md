# InterExchange Structure

To understand the **Interchange Structure**, you have to look at the massive "Rate Table" that Visa and Mastercard publish twice a year. It isn't just one fee; it is a complex grid of hundreds of different rates based on the specific risk and data provided during the transaction.

Think of it as a **"Risk vs. Reward"** matrix.

---

### 1. The Core Calculation

Interchange is almost always calculated as:



*Example: *

### 2. The Four Primary "Drivers" of the Rate

The specific rate a transaction "qualifies" for depends on these four factors:

#### **A. Card Type (The Funding Source)**

* **Regulated Debit:** Following the Durbin Amendment, cards issued by large banks ( $10B in assets) are capped at a very low rate: ****.
* **Unregulated Debit:** Small local banks and credit unions can charge higher rates.
* **Credit:** Much higher (average ****).
* **Commercial/Corporate:** The highest rates (often ****), as these cards come with high insurance and reporting perks.

#### **B. Entry Method (The Risk Factor)**

* **Card-Present (CP):** You physically tapped, dipped, or swiped.
* **Card-Not-Present (CNP):** Online or over the phone. These rates are higher because the merchant cannot verify the physical card.
* **Qualified vs. Mid-Qual vs. Non-Qual:** If a merchant doesn't settle their "batch" within 24 hours or fails to provide a zip code for an online order, the rate "downgrades" to a much more expensive tier.

#### **C. Merchant Category Code (MCC)**

The networks provide lower rates to businesses they want to encourage or that have low profit margins:

* **Public Sector:** Utilities and charities.
* **Emerging Markets:** Often includes fast food or "everyday" small purchases.
* **Supermarket/Grocery:** Very low percentage, but often a higher flat fee.

#### **D. Data Level (Level 1, 2, and 3)**

For B2B (Business-to-Business) transactions, if the merchant sends extra data (like a Tax ID or Invoice Number), the interchange rate **drops**.

* **Level 3 Data:** Can lower a corporate card rate by nearly ****.

---

### 3. Interchange Pricing Models for Merchants

Merchants generally choose one of three ways to pay these fees to their processor:

| Model | How it Works | Best For... |
| --- | --- | --- |
| **Flat Rate** | You pay one price (e.g., 2.6% + $0.10) regardless of the card type. | Small businesses (predictable). |
| **Interchange Plus** | You pay the "Raw" cost + a small markup (e.g., Interchange + 0.20%). | Growing businesses (most transparent). |
| **Tiered Pricing** | Transactions are grouped into "Qualified," "Mid-Qual," and "Non-Qual." | Generally avoided (often hides high fees). |

---

### 4. Summary: The 2026 "Cheat Sheet"

If you want the lowest interchange costs:

1. **Encourage Debit:** It is significantly cheaper than Credit.
2. **Tap or Dip:** Avoid "Keying in" card numbers manually.
3. **Settle Daily:** Ensure your credit card machine "closes out" every night to avoid "Downgrades."
4. **Use Level 3 Data:** If you sell to other businesses, use a gateway that sends invoice details.

