# Chapter 1 - Payments ISO 8583 Messaging

**ISO 8583** is the international standard for financial transaction card-originated messages. If you’ve ever swiped a credit card at a store or withdrawn cash from an ATM, an ISO 8583 message was the "language" used to authorize that transaction.

Even in 2026, despite the rise of newer XML-based standards like ISO 20022, ISO 8583 remains the global backbone for credit and debit card processing due to its extreme speed and efficiency.

---

### 1. The Core Structure

An ISO 8583 message is a compact string of data. Because it was designed in the 1980s when bandwidth was expensive, it doesn't use field names (like "Amount: $10"). Instead, it uses a **Bitmap** to tell the receiver which data is present at which position.

The message is divided into three main parts:

| Section | Name | Description | Example |
| --- | --- | --- | --- |
| **Part 1** | **MTI** | **Message Type Indicator:** A 4-digit code defining the message's purpose. | `0100` (Authorization Request) |
| **Part 2** | **Bitmaps** | A map (usually hex/binary) indicating which data fields are included. | `F238...` (Tells the system "Field 2 and 4 are here") |
| **Part 3** | **Data Elements** | The actual transaction data (Amount, Card Number, etc.). | `4242...` (The PAN) |

---

### 2. Deep Dive: The MTI (Message Type Indicator)

The MTI is the first thing a system reads. Each digit has a specific meaning:

* **1st Digit:** Version (e.g., `0` for the original 1987 version, `2` for the 2003 version).
* **2nd Digit:** Message Class (e.g., `1` for Authorization, `4` for Reversals).
* **3rd Digit:** Message Function (e.g., `0` for Request, `1` for Response).
* **4th Digit:** Message Origin (e.g., `0` for Acquirer/Merchant, `2` for Issuer/Bank).

> **Common MTI Examples:**
> * **0100:** "I'm a merchant, can this customer spend $50?" (Auth Request)
> * **0110:** "I'm the bank, yes they can." (Auth Response)
> * **0420:** "The transaction failed at the register, please cancel that charge." (Reversal)
> 
> 

---

### 3. The Bitmap: The "Traffic Controller"

Since not every transaction needs every field (an ATM withdrawal needs a PIN, but a grocery purchase might not), the **Bitmap** saves space. It is a string of 64 bits (or 128 if a secondary bitmap is used).

* If Bit #2 is "1", the system knows the next chunk of data is the **Primary Account Number (PAN)**.
* If Bit #4 is "1", the system knows the **Transaction Amount** is present.

---

### 4. Key Data Elements (Fields)

There are up to 128 standard fields. Here are the most critical ones:

* **DE 2:** Primary Account Number (Card Number).
* **DE 3:** Processing Code (e.g., "00" for Goods/Services, "01" for Cash Withdrawal).
* **DE 4:** Transaction Amount.
* **DE 7:** Transmission Date & Time.
* **DE 37:** Retrieval Reference Number (The unique "tracking ID" for the transaction).
* **DE 39:** Response Code (The famous **"00"** for Approved or **"51"** for Insufficient Funds).

---

### 5. ISO 8583 vs. ISO 20022

You may hear that ISO 8583 is "dying," but that’s an exaggeration.

* **ISO 8583 (Legacy):** Fast, compact, and optimized for high-volume card swipes. It's the "engine" of Visa and Mastercard.
* **ISO 20022 (Modern):** XML/JSON based. It's much "wordier" and carries way more data (like invoice details), making it better for bank-to-bank transfers and cross-border wires, but overkill for a simple coffee purchase.

---

### Summary

ISO 8583 is a highly optimized, linear messaging format. It allows a bank in New York to instantly understand a transaction request coming from a street vendor in New Delhi, even if they use completely different hardware.

# Chapter 2 - Payments ISO 8583 Messaging Vs ISO20022

**ISO 20022 did not replace ISO 8583.** Instead, it replaced the **legacy Fedwire (FAIM)** and **SWIFT (MT)** formats used for large-scale, bank-to-bank transfers. In the world of finance, these standards live in two different "neighborhoods."

---

### 1. The "Neighborhood" Difference

Think of these as two different types of transport:

* **ISO 8583 (The Sports Car):** It is built for **speed and high volume**. It is still the king of retail. Every time you buy a coffee or use an ATM, ISO 8583 is doing the work. It is small, fast, and does exactly one job: authorizing card transactions.
* **ISO 20022 (The Semi-Truck):** It is built for **capacity and detail**. It is used for the "heavy lifting" like billion-dollar corporate wires, cross-border settlements, and payroll. It carries massive amounts of data (invoices, addresses, tax IDs) that ISO 8583 simply cannot hold.

### 2. What exactly did the Fed replace in July 2025?

When the Fed migrated, they replaced their **proprietary wire format (FAIM)**.

* **Before July 2025:** If a bank wanted to send a wire, they used a format called FAIM (or SWIFT MT for international). These were like "old telegrams"—short, text-only, and messy.
* **After July 2025:** They must use the **ISO 20022 (XML)** format. This is like moving from a telegram to a detailed digital form.

### 3. Will ISO 20022 *eventually* replace ISO 8583?

As of February 2026, there is a movement in that direction, but we aren't there yet.

* **The Goal:** To have one single language for all finance. ISO 20022 has a "card" version (called **ATICA**) designed to replace ISO 8583.
* **The Reality:** Visa and Mastercard have billions of dollars invested in ISO 8583 infrastructure. Moving them is like trying to replace every electrical outlet in the world simultaneously. It will likely take another decade before ISO 20022 becomes the standard for your daily card swipe.

---

### Summary Table: 2026 Status

| Feature | ISO 8583 | ISO 20022 |
| --- | --- | --- |
| **Primary Use** | **Retail:** Credit cards, POS, ATMs. | **Wholesale:** Fedwire, SWIFT, Cross-border. |
| **Data Capacity** | Low (Small, fast bits). | High (Rich, structured XML). |
| **Fed Status** | **Still Active** for card networks. | **Mandatory** for Fedwire since July 2025. |
| **Speed** | Milliseconds (Authorization). | Seconds to Minutes (Settlement). |

#Chapter 3 Interexchange Fees

An **Interchange Fee** is the "swipe fee" paid by a merchant's bank (the acquirer) to the customer’s bank (the issuer) every time a credit or debit card is used.

While the customer never sees this fee, it is the reason some small businesses have a "$10 minimum" for credit card purchases. In the complex plumbing of a transaction, interchange is the largest portion of the total "Merchant Discount Rate" (the total fee a store pays to accept cards).

---

### 1. Who gets the money?

Contrary to popular belief, the fee doesn't mostly go to Visa or Mastercard.

* **The Issuer (90%):** Your bank (e.g., Chase, Amex, Wells Fargo) gets the lion's share. This money covers their risk of fraud, the cost of the interest-free grace period, and—most importantly—the **rewards/points** you earn.
* **The Network (10%):** Visa or Mastercard takes a small "switch fee" or "assessment fee" for providing the infrastructure (the ISO 8583 rails we discussed).

---

### 2. The Three Main Components

Interchange isn't a single flat rate; it is a calculation based on three variables:

#### **A. The Card Type (The "Who")**

* **Debit vs. Credit:** Debit fees are usually capped (around **0.05% + $0.21** for large banks due to the Durbin Amendment). Credit fees are much higher (often **1.5% to 2.5%**).
* **Rewards Tier:** A "Basic" card costs the merchant less. A "Premium" card (like a Chase Sapphire Reserve or Amex Platinum) has a much higher interchange fee because the merchant is effectively subsidizing your travel points.

#### **B. The Merchant Category (The "Where")**

The IRS and Card Networks use **MCC Codes** (Merchant Category Codes).

* **High Risk/High Margin:** Luxury jewelry stores often pay higher rates.
* **Low Margin/Public Good:** Charities, utilities, and large grocery stores often get "Incentive Rates" which are much lower.

#### **C. Transaction Method (The "How")**

* **Card-Present (CP):** Swiping or "dipping" the chip in person. This is the lowest fee because the risk of fraud is lower.
* **Card-Not-Present (CNP):** Online shopping or phone orders. These have the **highest interchange fees** because the risk of a stolen card number is much higher.

---

### 3. A Typical Fee Breakdown (Example)

If you buy a **$100** jacket at a local boutique with a premium Rewards Credit Card, the merchant might pay a total fee of **$2.80**. That $2.80 is split like this:

| Component | Amount | Where it goes |
| --- | --- | --- |
| **Interchange Fee** | **$2.10 (2.1%)** | To your bank (The Issuer) |
| **Assessment Fee** | **$0.13 (0.13%)** | To the Network (Visa/MC) |
| **Markup/Processing** | **$0.57** | To the merchant's bank (The Acquirer) |
| **Total Cost** | **$2.80** | **Merchant receives $97.20** |

---

### 4. 2026 Regulatory Landscape

As of February 2026, interchange fees are under heavy fire:

* **The Credit Card Competition Act:** There is ongoing legislative pressure to force banks to offer a second routing network (besides Visa/MC), which could lower these fees.
* **Surcharging Rules:** More states have recently legalized "Surcharging," where a merchant can legally pass that 2-3% fee directly to you at the register if you choose to use a credit card instead of cash or debit.

> **Pro-Tip:** This is why "Cash Back" and "Travel Points" exist. They are literally funded by the interchange fees that merchants pay. If you use a "1% cash back" card, the bank is just giving you a slice of the 2% interchange fee they collected from the store.

