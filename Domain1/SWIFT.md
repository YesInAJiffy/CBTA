# SWIFT

**SWIFT** (Society for Worldwide Interbank Financial Telecommunication) is the global messaging network that financial institutions use to securely transmit information and instructions, such as money transfer orders.

A common misconception is that SWIFT actually "moves" the money. It does not. Instead, it is the **"WhatsApp of Banking"**—a secure communication layer that tells banks *where* to move the funds that they hold in their own accounts.

---

### 1. How SWIFT Works: The Messaging Chain

Since banks don't have a single giant vault, they move money through a network of **Correspondent Banking** relationships.

* **The Message:** When you send a wire, your bank sends a standardized SWIFT message to the recipient's bank.
* **The "Rails":** The banks use **Nostro and Vostro** accounts (mirrored accounts they hold with each other) to settle the actual cash.
* **The Intermediaries:** If Bank A and Bank B don't have a direct relationship, the SWIFT message is routed through a "middleman" bank (Intermediary) that has a relationship with both.

---

### 2. Identifying the Players: BIC and IBAN

To ensure the "message" reaches the right person, SWIFT uses two critical codes:

* **BIC (Bank Identifier Code):** Often called the **SWIFT Code**. It identifies the **Bank**.
* *Example:* `CHASUS33` (Chase Bank, USA).


* **IBAN (International Bank Account Number):** Identifies the **Specific Account**.
* *Example:* `GB29 UKRY 1234 5678...` (A specific account in the UK).



> **Think of it this way:** The **BIC** is the zip code for the building; the **IBAN** is the specific mailbox inside.

---

### 3. The 2025/2026 "ISO 20022" Revolution

As we discussed earlier with the US Fed, SWIFT has officially moved into the **ISO 20022 era**.

* **The Cutover (Nov 2025):** The legacy "MT" (Message Type) format was decommissioned for most major payment types.
* **Current Status (2026):** All banks are now required to use the **MX** (XML-based) format.
* **The Benefit:** Old messages were limited to short text. New ISO 20022 messages can carry vast amounts of data—like actual building numbers in addresses, full tax IDs, and digital invoice attachments.

---

### 4. SWIFT gpi (The "Amazon Tracker" for Money)

One of the biggest complaints about SWIFT was that money would "disappear" for days while moving through intermediaries. In response, SWIFT launched **gpi (Global Payments Innovation)**.

* **Tracking:** Every payment is assigned a **UETR** (Unique End-to-End Transaction Reference).
* **Transparency:** You can see exactly where the money is, which bank is currently holding it, and how much in fees each middleman has deducted.
* **Speed:** Nearly **50% of gpi payments** are now credited in less than 30 minutes.

---

### 5. Summary: SWIFT vs. Other Systems

| Feature | SWIFT | Fedwire / CHIPS |
| --- | --- | --- |
| **Role** | Messaging Network (The Instruction) | Settlement System (The Actual Money) |
| **Reach** | Global (200+ countries) | Primarily Domestic (USA) |
| **Format** | **ISO 20022** (as of 2026) | **ISO 20022** (as of 2025) |
| **Speed** | Minutes to Days | Real-time / Same-day |

# Nostro Vostro Accounts

As we move into international wires, **Nostro** and **Vostro** are the specialized accounting terms banks use to keep track of the money they hold for each other across borders.

They actually refer to the **exact same account**, but the name changes depending on which bank is talking.

---

### 1. The Literal Meaning

The terms come from Italian and Latin, dating back to the 14th-century Mediterranean merchants:

* **Nostro** means **"Ours"** ("Our account with you").
* **Vostro** means **"Yours"** ("Your account with us").

---

### 2. The Perspective: Two Sides of One Ledger

Imagine two banks: **HDFC Bank (India)** and **J.P. Morgan Chase (USA)**. HDFC wants to be able to pay people in US Dollars, so they open a USD account *inside* J.P. Morgan in New York.

| Bank | How they refer to the account | The logic |
| --- | --- | --- |
| **HDFC (India)** | **Nostro Account** | "This is **our** money, but it is sitting in your bank in New York." |
| **J.P. Morgan (USA)** | **Vostro Account** | "This is **your** money, and we are holding it for you in our bank." |

---

### 3. Why are these accounts necessary?

Banks don't literally ship boxes of cash to each other when you send a wire. Instead, they "settle" the debt by adjusting the balances in these accounts.

* **Global Reach:** Your local bank doesn't need a building in every country. They just need a Nostro account with a "Correspondent Bank" that already has a building there.
* **Currency Availability:** By keeping a Nostro account in USD, a bank in India always has "pre-funded" dollars ready to go. They don't have to go to the open market to buy dollars for every single small customer wire.
* **Speed:** When a bank uses its Nostro account to pay a vendor, it's essentially a local transfer within the foreign country’s banking system (e.g., from one US bank to another), which is much faster than an "international" move.

---

### 4. Real-World Example: Paying your US Vendor

If you are in New Delhi and you send **$1,000** to a vendor in New York:

1. You pay your Indian bank in **Rupees**.
2. Your Indian bank sends a **SWIFT message** to its correspondent bank in the US (where it has a **Nostro** account).
3. The US correspondent bank sees the message and says, *"Okay, I will take $1,000 out of HDFC's **Vostro** account and give it to the vendor's bank here in New York."*
4. **Result:** The money never actually crossed the ocean; only the "instruction" (the SWIFT message) did.

---

### 5. Summary: Key Differences

| Feature | Nostro Account | Vostro Account |
| --- | --- | --- |
| **Translation** | "Ours" | "Yours" |
| **Account Owner** | The Domestic Bank (sending the money) | The Foreign Bank (holding the money) |
| **Currency** | Foreign Currency (e.g., USD, EUR) | Domestic Currency (e.g., INR) |
| **Asset/Liability** | **Asset** (It's their cash) | **Liability** (They owe it to the other bank) |

# Correspondent vs Respondent Banks

To understand a **Correspondent Bank**, think of it as a "financial ambassador."

Since it is impossible for every bank in the world to have a physical building in every other country, they form **bilateral partnerships**. A Correspondent Bank is a bank that provides services (like wire transfers, currency exchange, and check clearing) on behalf of another bank in a different geographical location.

The **Nostro** and **Vostro** accounts are the actual "ledger books" used to manage this relationship.

---

### 1. The Relationship Hierarchy

In a typical international transaction, there are two roles:

* **The Respondent Bank:** The "client" bank that needs help reaching a foreign market.
* **The Correspondent Bank:** The "service provider" bank that has a local presence and access to the local clearing system in that foreign market.

---

### 2. How the Accounts Relate

A correspondent relationship is officially established the moment a **Nostro/Vostro** account is opened. They are the same account, but the name depends on who is looking at it:

| Term | Perspective | Role in the Relationship |
| --- | --- | --- |
| **Nostro** ("Ours") | **The Respondent Bank** | "This is our asset (cash) sitting in the correspondent's vault." |
| **Vostro** ("Yours") | **The Correspondent Bank** | "This is a liability (money we owe) to the respondent bank." |

**Relationship Example:**
If **State Bank of India (SBI)** wants to help its customers send money to New York but doesn't have a massive US presence, it partners with **J.P. Morgan Chase**.

* **J.P. Morgan** is the **Correspondent Bank**.
* **SBI** is the **Respondent Bank**.
* The USD account they share is **SBI's Nostro** and **J.P. Morgan's Vostro**.

---

### 3. The "Loro" Account: The Third Perspective

There is a third term often used when a bank talks about a relationship *between two other banks*.

* **Loro** means **"Theirs."**
* **Usage:** If **HDFC Bank** is talking to **SBI** and refers to the money SBI has sitting at J.P. Morgan, HDFC calls it a **Loro Account**.
* **Translation:** "Their account with them."

---

### 4. Why this matters for your Wire Transfers

When you send an international wire from India to the US, the money doesn't actually travel across the ocean. Instead, a "relay race" happens using these accounts:

1. **Instruction:** Your bank sends a **SWIFT message** to the Correspondent Bank.
2. **Settlement:** The Correspondent Bank sees the message and **debits** your bank’s **Vostro** account (decreasing what they owe your bank).
3. **Local Payout:** The Correspondent Bank then sends that money through the **local** US system (like Fedwire or ACH) to the final recipient.

### Summary

* **Correspondent Bank:** The **Entity** (The partner bank).
* **Nostro/Vostro:** The **Account** (The tool they use to move the money).
* **SWIFT:** The **Communication** (The instructions sent between them).

# Intermediary Fees

In 2026, the cost of sending an international wire is rarely just the "sending fee" your bank quotes you. Because money often travels through a **Correspondent/Intermediary Bank**, additional fees are deducted along the way.

How these fees are handled depends on a specific **SWIFT Instruction Code** (OUR, SHA, or BEN) that the sender selects at the start.

---

### 1. The Intermediary Bank Fees

If your bank in India doesn't have a direct relationship with the recipient's bank in the US, an **Intermediary Bank** acts as the bridge.

* **Typical Fee:** Between **$10 and $50** per intermediary.
* **The "Hidden" Deductible:** These fees are often deducted directly from the principal amount. If you send $1,000, the recipient might only get $970 because an intermediary took a $30 "handling fee" without an invoice.

---

### 2. The Three Fee Models (OUR, SHA, BEN)

When you fill out a wire transfer form, you will usually see these three options. This tells the banks who should pay the intermediary and receiving costs.

| Code | Name | Who Pays Intermediary/Receiving Fees? | Result for the Recipient |
| --- | --- | --- | --- |
| **OUR** | **Sender Pays** | **You (the Sender)** pay a higher upfront fee to your bank. | They receive the **Exact Amount** (e.g., $1,000 sent = $1,000 received). |
| **SHA** | **Shared** | **Split.** You pay your bank's fee; they pay the rest. | They receive the amount **minus deductions** (e.g., $975 received). |
| **BEN** | **Beneficiary Pays** | **The Recipient** pays everything. | They receive the amount **minus ALL fees** (e.g., $940 received). |

> **Pro-Tip:** If you are paying a specific bill (like a university tuition or a visa fee), **always choose "OUR."** Otherwise, the recipient will be short by $20–$30, and your bill might be marked as "unpaid."

---

### 3. Typical 2026 Fee Breakdown (India to US)

For a standard $1,000 transfer from an Indian bank to a US bank, here is the math you might see:

1. **Sending Bank Fee (India):** ₹500 – ₹1,000 ($6 – $12)
2. **Exchange Rate Markup:** 1% – 3% ($10 – $30 "hidden" in the rate)
3. **Intermediary Fee:** $15 – $30 (Deducted if SHA/BEN)
4. **Receiving Bank Fee (US):** $15 – $25 (Deducted if SHA/BEN)

---

### 4. How Correspondent Banking Relates to Fees

The more "exotic" the currency or the smaller the bank, the more intermediaries are involved.

* **Direct Relationship:** If HDFC has a Nostro account at Chase, there is **0 intermediary fee** because they talk directly.
* **Indirect Relationship:** If a small rural credit union in India sends to a small bank in Kansas, the money might pass through **two or three** intermediary banks. Each one will take their own $15–$20 cut.

### Summary

The **Correspondent Bank** provides the "plumbing," and the **Nostro/Vostro** accounts provide the "water" (the funds). The **SWIFT codes (OUR/SHA/BEN)** are the instructions that decide who pays for the plumbing maintenance.

# SWIFT MX Message Types

The shift from **MT (Message Type)** to **MX (Message Type XML)** is a move from a 40-year-old "telegram" style of banking to a modern, data-rich digital format.

As we are now in **February 2026**, the major transition deadline (November 2025) has passed. Most global banks have finished migrating their core payment instructions to MX. Here is the breakdown of what the MX message actually is and how it works.

---

### 1. The Anatomy of an MX Message

Unlike the old MT messages, which used rigid tags like `:20:` or `:50K:`, MX messages are written in **XML**. This makes them flexible and readable by computers without needing special "banking-only" software.

An MX message name (like **pacs.008.001.02**) tells you exactly what it is:

* **Business Area (pacs):** The first four letters. *pacs* = Payments Clearing and Settlement.
* **Message ID (008):** The core function. *008* is a Customer Credit Transfer.
* **Variant (001):** Usually identifies a specific market flavor.
* **Version (02):** The current technical version of the message.

---

### 2. The Four "Families" of MX

In 2026, you will mostly encounter these four prefixes in bank communications:

| Prefix | Full Name | Purpose | MT Equivalent |
| --- | --- | --- | --- |
| **pacs** | **Pa**yments **C**learing & **S**ettlement | Bank-to-bank movement of funds. | MT103, MT202 |
| **pain** | **Pa**yment **In**itiation | A customer telling their bank to start a payment. | MT101 |
| **camt** | **Ca**sh **M**anagemen**t** | Reporting, bank statements, and investigations. | MT940, MT950 |
| **acmt** | **Ac**count **M**anagemen**t** | Opening or closing bank accounts. | New/N/A |

---

### 3. Why is MX better than MT?

The move wasn't just about changing the file format; it was about the **data quality**.

* **Structured Addresses:** In MT, an address was just 4 lines of text. In MX, it is broken into: *Street, Building Number, City, State, Country Code.* This prevents "Compliance False Positives" that used to delay wires.
* **Extended Remittance:** MT was limited to 140 characters for a description. MX allows you to attach **thousands of characters**, including full invoice lists, tax breakdowns, and even links to digital documents.
* **Ultimate Parties:** MX allows the message to identify the *actual* original sender and the *actual* final receiver, even if five different banks are involved in the middle.

---

### 4. The 2026 Reality: "Truncation" and "Hybrid Addresses"

Even though we are past the 2025 deadline, you should be aware of two things happening right now in early 2026:

1. **Reporting Delay:** While *Payments* (pacs) moved in 2025, many banks (like J.P. Morgan and Citi) have deferred **Reporting** (camt.053 statements) until **late 2026**. This means your bank statement might still look like the old format for a few more months.
2. **The Address Deadline:** Starting in **November 2026**, SWIFT will stop accepting "Unstructured" addresses entirely. Banks are currently in a "Hybrid" phase, where they are forcing clients to start providing building numbers and street names separately.

---

### Summary Table

| Feature | MT (Legacy) | MX (Modern 2026) |
| --- | --- | --- |
| **Format** | Text / Swift-FIN | XML |
| **Characters** | Restricted (Latin only) | Unlimited (Supports Unicode/Local Languages) |
| **Data Structure** | Flat / Unstructured | Highly Structured / Granular |
| **Interoperability** | Low (Proprietary) | High (Standardized across 70+ countries) |

# 4 Payment families of MX

While there are dozens of MX message types, you really only need to know a handful to understand 90% of the world's financial traffic in 2026.

The **pacs** and **camt** families are the most active "workhorses," as they handle the actual movement and reporting of money between banks.

---

### 1. The `pacs` Family (The Workhorses)

These are used **bank-to-bank**. Every time a wire moves through the Fed or SWIFT, one of these is flying through the air.

| Message ID | Use Case | MT Equivalent |
| --- | --- | --- |
| **pacs.008** | **Customer Credit Transfer.** This is the "standard wire." Used when you send money to another person or business. | MT103 |
| **pacs.009** | **Financial Institution Transfer.** Used when one bank pays another bank (e.g., settling a debt or moving their own liquidity). | MT202 |
| **pacs.002** | **Payment Status Report.** The "receipt" or "error message." If a payment is rejected or accepted, this message carries the reason code. | MT199 / MT299 |
| **pacs.004** | **Payment Return.** Used to "undo" a payment and send the funds back to the original sender. | New (No direct MT) |

---

### 2. The `camt` Family (The Reporting)

These are used for **reporting and investigations**. This is what allows your accounting software to "see" your bank balance.

| Message ID | Use Case | MT Equivalent |
| --- | --- | --- |
| **camt.053** | **Bank Statement.** The "End of Day" statement. This is the master file used for reconciliation. | MT940 / MT950 |
| **camt.052** | **Intraday Report.** A "sneak peek" at your balance in the middle of the day. | MT942 |
| **camt.054** | **Debit/Credit Notification.** A real-time alert that a specific payment just hit (or left) your account. | MT900 / MT910 |

---

### 3. The `pain` Family (The Initiation)

These are used **customer-to-bank**. You usually use these if you are a corporate treasurer uploading a large file of payments to your bank.

* **pain.001:** The "Instruction." You send this to your bank to say, "Please pay these 100 vendors." (Replaces MT101).
* **pain.002:** The "Feedback." The bank sends this back to you to say, "We received your file; 98 payments were okay, 2 were rejected."

---

### 4. Which one is "King"?

If you only remember one, make it **pacs.008**.
It is the most common message in the world because it represents the fundamental act of **one person paying another person**. In the 2026 banking world, almost everything else exists just to support or report on the **pacs.008**.

### Summary of Popularity (2026)

1. **pacs.008** (The Actual Payment) — **High Volume**
2. **pacs.002** (The Status Update) — **High Volume**
3. **camt.053** (The Daily Statement) — **Daily Routine**
4. **pain.001** (The Bulk Upload) — **Common for Businesses**

