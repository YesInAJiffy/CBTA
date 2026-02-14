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

# SWIFT Services

Beyond the core messaging, SWIFT provides a suite of high-level services that act as the "control tower" for global banking. As of 2026, these tools—**gpi**, **Sanctions Screening**, and **RMA**—are no longer optional luxuries; they are the standard for secure, transparent international trade.

---

### 1. SWIFT gpi (Global Payments Innovation)

If traditional SWIFT is a letter in the mail, **gpi** is a high-priority FedEx package with real-time GPS tracking.

* **The UETR (Unique End-to-End Transaction Reference):** Every gpi payment is assigned a 36-character tracking code. This stays with the payment across all banks in the chain, allowing you to see exactly where your money is at any second.
* **Speed:** In 2026, roughly **50% of gpi payments** are credited within 30 minutes, and nearly 100% within 24 hours.
* **Fee Transparency:** It forces intermediary banks to "show their work." You can see exactly what was deducted for "lifting fees" or currency exchange before the money hits the destination.
* **Stop and Recall (gSRP):** This is a "panic button." If you realize you’ve sent money to a fraudulent account, gpi allows a bank to send an instant "stop" signal that can halt the payment even while it is in transit between banks.

---

### 2. Sanctions Screening

This is the "security checkpoint" of the SWIFT network. To prevent money laundering and terrorism financing, every bank must check names against global watchlists (like OFAC in the US or the UN list).

* **The Problem:** Smaller banks often struggle to keep up with the thousands of daily updates to sanctions lists.
* **The SWIFT Service:** SWIFT provides a **cloud-hosted screening service**. When a bank sends a message, it is automatically routed through SWIFT’s filters.
* **Fuzzy Matching:** The system is smart enough to flag "Jon Doe" even if it's spelled "John Dough" or "J. Doe" to ensure criminals don't slip through via typos.
* **Blocking vs. Non-Blocking:** Banks can set the service to "Block" (hold the payment for review) or just "Alert" (notify the compliance team after the fact).

---

### 3. RMA (Relationship Management Application)

RMA is the **"Digital Gatekeeper."** It is a filter that allows a bank to control exactly who can send them messages and what *kind* of messages they are willing to receive.

* **The Purpose:** It prevents "spam" and unauthorized traffic. Without an RMA "handshake," Bank A cannot send a payment instruction to Bank B.
* **How it Works:** Before exchanging money, two banks must exchange an **RMA Authorization**. They agree on:
* **Which categories** of messages are allowed (e.g., "Only payments, no trade finance").
* **Which BIC codes** are authorized to send them.


* **Why it matters:** It is a primary defense against cyberattacks. If a hacker takes over a bank's SWIFT terminal, they can only send fraudulent wires to banks that have a pre-existing RMA relationship with that terminal.

---

### Summary: How they work together

| Service | Real-World Analogy | Primary Benefit |
| --- | --- | --- |
| **SWIFT gpi** | Amazon Package Tracker | **Certainty:** Knowing exactly when the money arrives. |
| **Sanctions Screening** | Airport Security / X-Ray | **Safety:** Keeping the bank out of legal trouble. |
| **RMA** | A "Contact Whitelist" | **Control:** Only talking to banks you trust. |

# Difference betweeen MT and MX

As of **February 2026**, the global banking community has effectively crossed the finish line of the "Great Migration." The transition from **MT (Message Type)** to **MX (Message Type XML)** is officially complete for cross-border payments, following the November 2025 deadline.

Here is the definitive breakdown of the differences between the two standards:

---

### 1. The Core Technology: Text vs. XML

* **MT (Legacy):** Based on the **ISO 15022** standard. It uses a proprietary, text-based "tag" format (e.g., `:20:`, `:50K:`) that looks like a telegram. It is "flat," meaning data follows a strict, non-nested sequence.
* **MX (Modern):** Based on the **ISO 20022** standard. It uses **XML (Extensible Markup Language)**. This allows for a **hierarchical/nested structure**, meaning a computer can understand that "Building 5" belongs to "Main Street," which belongs to "London," without needing a human to guess.

### 2. Data Capacity (The "HD" Upgrade)

The most significant difference is the **volume and quality of data** each message can carry.

| Feature | SWIFT MT | SWIFT MX (ISO 20022) |
| --- | --- | --- |
| **Character Set** | Limited (Latin/ASCII only) | **Universal (Unicode/UTF-8)**; supports Chinese, Arabic, etc. |
| **Address Info** | 4 lines of 35 characters (Unstructured) | **Unlimited & Structured** (Building, Street, Postcode, etc.) |
| **Remittance Info** | Max 140 characters | **Unlimited** (Can include full invoice details or URLs) |
| **Parties** | Limited to basic Sender/Receiver | Can identify **Ultimate Debtor** and **Ultimate Creditor** |

### 3. The "Truncation" Risk (2026 Context)

In early 2026, many banks are still using "Translation" tools to convert incoming MX messages back into MT format for their older internal systems.

* **The Problem:** Because an MX message is much "bigger" than an MT message, a lot of the rich data (like the specific street address or invoice number) gets **truncated** (cut off) during the down-conversion.
* **The Result:** This is why some wires in 2026 still trigger compliance "red flags"—the bank's old system can't see the full data provided in the original MX message.

### 4. Naming Conventions

You can identify which generation a message belongs to just by its name:

* **MT Names (3 Digits):** * **MT103:** Single Customer Credit Transfer.
* **MT202:** Bank-to-Bank Transfer.
* **MT940:** Customer Statement.


* **MX Names (Family.Function.Variant):**
* **pacs.008:** The replacement for MT103 (Payments).
* **pacs.009:** The replacement for MT202 (Settlement).
* **camt.053:** The replacement for MT940 (Reporting).



---

### 5. Why the change actually happened

1. **Compliance:** MX allows for "Structured Name and Address," which dramatically reduces **False Positives** in sanctions screening (e.g., distinguishing "John Smith" from "John Smith Jr.").
2. **Straight-Through Processing (STP):** Because the data is so organized, computers can process payments automatically without a human having to manually fix "broken" addresses or vague payment descriptions.
3. **Future-Proofing:** XML is the language of the internet. By moving to MX, banks can now easily integrate with Fintech APIs, AI-driven fraud detection, and instant payment rails like FedNow.

# Understand MT103 fields 


To master the **MT103** (Single Customer Credit Transfer), you need to look at its "Blocks." A SWIFT message isn't just a list of fields; it's a structured file with five distinct sections.

Most of what people call "MT103 fields" live in **Block 4 (The Text Block)**.

---

### 1. The 5-Block Structure

Before you get to the payment details, the "Envelope" provides the routing:

* **{1:} Basic Header:** Sender's BIC, session number.
* **{2:} Application Header:** Direction (Input/Output), Message Type (103), Receiver's BIC.
* **{3:} User Header:** Includes the **Tag 121 (UETR)**—the 36-character tracking ID for gpi.
* **{4:} Text Block:** The actual payment data (the fields we discuss below).
* **{5:} Trailer:** Checksums and security signatures.

---

### 2. Mandatory Fields (The Must-Haves)

If any of these are missing or incorrectly formatted, the SWIFT network will reject the message instantly.

| Tag | Field Name | Format & Example | Description |
| --- | --- | --- | --- |
| **:20:** | Sender's Reference | `16x` (Max 16 chars) | The unique ID assigned by the sending bank. |
| **:23B:** | Bank Operation Code | `4!c` (CRED) | Usually `CRED`. Tells the bank to credit the receiver. |
| **:32A:** | Value Date/Currency/Amount | `DateCurAmt` | Example: `260214USD1000,00` (Feb 14, 2026, $1k). |
| **:50a:** | Ordering Customer | Name & Address | The sender's info. Uses Option **A, F, or K**. |
| **:59a:** | Beneficiary Customer | `/Acc + Name` | The recipient's info. Usually `/` followed by an IBAN. |
| **:71A:** | Details of Charges | `3!a` (OUR/SHA/BEN) | Decide who pays the fees (Sender, Shared, or Receiver). |

---

### 3. Optional but Critical Fields

These fields determine the "Path" the money takes.

| Tag | Field Name | Usage |
| --- | --- | --- |
| **:33B:** | Instructed Amount | The amount the customer *originally* asked to send (if different from 32A). |
| **:52A:** | Ordering Institution | The BIC of the bank that initiated the transfer for the customer. |
| **:56A:** | Intermediary Institution | The "Middleman" bank used if there is no direct relationship. |
| **:57A:** | Account With Institution | The BIC of the **Recipient’s Bank**. |
| **:70:** | Remittance Info | Up to 4 lines of 35 chars for "Invoice #123" or "Gift." |
| **:72:** | Sender to Receiver Info | Instructions for the next bank (e.g., `/REJT/` for a return). |

---

### 4. Field 50/59 Options (A, F, K)

You’ll often see a letter after the tag. This tells you how the data is formatted:

* **Option A:** Used for **BIC** (Standardized bank code).
* **Option K:** Used for **Name and Address** (Free-format text, 4 lines).
* **Option F:** Used for **Structured Data** (Identifying if it's a person or a company).

---

### 5. Summary Cheat Sheet for 2026

In the current era of ISO 20022, the MT103 is often "mapped" into a **pacs.008**. The main friction point today is **Tag 50 and 59 addresses**.

> **Compliance Note:** In 2026, most banks will reject an MT103 if the address in Tag 50 or 59 is just a single line. They now demand "Structured-like" info (Street, City, Country) to satisfy the requirements of the new MX format.

# Know ISO 20022 message families : pain/pacs/camt

To "know" the ISO 20022 message families, you have to understand the **Payment Lifecycle**.

In the old MT world, we had one big bucket for everything (100-series, 200-series, 900-series). In the MX world, we use three distinct families that pass the "baton" to each other as a payment moves from a customer to a bank, then through the clearing system, and finally onto a statement.

---

### 1. `pain` (Payment Initiation)

**Direction:** Customer  Bank
The `pain` family is the "Request." It is used by individuals or businesses to tell their bank what to do.

* **pain.001 (Customer Credit Transfer Initiation):** The most common. It’s you telling the bank, "Please pay my landlord $1,000." A single `pain.001` can contain a batch of thousands of payments.
* **pain.002 (Payment Status Report):** The bank's reply to the customer. "We received your request; 99 payments are pending, 1 failed because of an invalid IBAN."
* **pain.008 (Customer Direct Debit Initiation):** Used by a company (like a gym) to tell their bank to "pull" money from their members' accounts.

---

### 2. `pacs` (Payments Clearing and Settlement)

**Direction:** Bank  Clearing System  Bank
The `pacs` family is the "Execution." These are the heavy-duty messages that move actual value between financial institutions.

* **pacs.008 (FI to FI Customer Credit Transfer):** The king of MX messages. It is the interbank version of your payment. It carries all the rich data (structured addresses, ultimate parties) that the original `pain.001` started.
* **pacs.009 (Financial Institution Credit Transfer):** Used when banks pay *each other* (e.g., settling a currency trade or moving their own liquidity).
* **pacs.002 (FI to FI Payment Status):** Bank-to-bank reporting. If a payment is stuck at an intermediary bank, they use this to tell the sending bank why.
* **pacs.004 (Payment Return):** The "undo" button. If a payment reaches the final bank but the account is closed, the bank sends the money back using this message.

---

### 3. `camt` (Cash Management)

**Direction:** Bank  Customer
The `camt` family is the "Reporting." It tells the account owner what happened to their money after the dust has settled.

* **camt.053 (Bank to Customer Statement):** The master file. It is your daily bank statement in XML format, replacing the old MT940.
* **camt.052 (Account Report):** An "intraday" report. It shows your current balance and any transactions that have hit so far today (replacing MT942).
* **camt.054 (Debit/Credit Notification):** A real-time "ping" for a specific transaction. Instead of a whole statement, it’s just one notification: "You just received $5,000."
* **camt.056 (Payment Cancellation Request):** A bank-to-bank message used to try and "claw back" a payment that was sent by mistake.

---

### The 2026 "Chain of Events"

Here is how they all connect in a single transaction:

1. **Initiation:** You send a **pain.001** to your bank.
2. **Acknowledgment:** Your bank sends you a **pain.002** (Accepted).
3. **Clearing:** Your bank sends a **pacs.008** to the recipient's bank.
4. **Notification:** The recipient's bank sends them a **camt.054** (You've got money!).
5. **Reporting:** At the end of the day, you receive a **camt.053** statement showing the $1,000 deduction.

### Summary Table

| Family | Purpose | Analogy | Main Character |
| --- | --- | --- | --- |
| **pain** | **Initiation** | The Order (at a restaurant) | `pain.001` |
| **pacs** | **Settlement** | The Cooking & Delivery | `pacs.008` |
| **camt** | **Reporting** | The Receipt | `camt.053` |

# Understand SWIFT role and clearing

The best way to understand the difference between **SWIFT** and **Clearing** is to think of a restaurant: **SWIFT is the waiter** (taking the order), and **Clearing is the kitchen** (preparing and finalizing the meal).

By 2026, the two work together seamlessly via the ISO 20022 standard, but they perform very different jobs in the payment lifecycle.

---

### 1. SWIFT: The Messaging Layer

SWIFT is **communication**. It does not hold money, and it does not settle accounts.

* **Role:** It provides a secure, standardized "social network" for banks to talk.
* **Action:** When you send a wire, SWIFT carries the instruction (e.g., a **pacs.008** message) from your bank to the next bank.
* **Analogy:** It’s the **WhatsApp** of banking. It delivers the "Hey, pay this person $500" message.

### 2. Clearing: The Accounting Layer

Clearing is **calculation and validation**. It happens *after* the message is received but *before* the money is finally moved.

* **Role:** A Clearing House (like the **ACH** or **CHIPS** in the US) checks the "math" of the transaction.
* **Action:** It verifies that the sender has enough money, confirms the account numbers exist, and calculates the "net" amount each bank owes the other at the end of the day.
* **Analogy:** It’s the **Ledger**. It makes sure the debt is recorded correctly before anyone is actually paid.

---

### 3. Comparison Table (2026 Context)

| Feature | SWIFT | Clearing System (ACH, CHIPS, T2) |
| --- | --- | --- |
| **Primary Job** | **Messaging** (Instructions) | **Netting & Validation** (Math) |
| **Does it move funds?** | No | No (Clearing prepares, **Settlement** moves) |
| **Global Reach** | 200+ Countries | Primarily Domestic or Regional |
| **Message Type** | **ISO 20022** (pacs, camt) | **ISO 20022** (pacs, camt) |
| **Example** | SWIFT gpi | The Clearing House (TCH) / FedNow |

---

### 4. How They Interact (The Workflow)

In a modern 2026 payment, the two are "interlinked" through a process often called **FINplus** or a **Market Infrastructure (MI)** connection:

1. **SWIFT Step:** Bank A sends a **pacs.008** message via the SWIFT network.
2. **Clearing Step:** The message hits a **Clearing House** (like the Federal Reserve). The Clearing House validates the transaction and checks if Bank A has enough "Liquidity" (cash) in its account.
3. **Settlement Step:** The actual funds are transferred between the banks' accounts at the Central Bank.
4. **SWIFT Step:** SWIFT delivers the final "confirmed" message to Bank B, telling them they can now credit the customer's account.

---

### 5. Why the distinction is blurred in 2026

With the rise of **Instant Payments** (like FedNow and RTP), the "Messaging" and "Clearing" happen almost simultaneously. However, they are still technically separate:

* **SWIFT** provides the **Standard** (the XML language).
* **The Clearing House** provides the **Rulebook** (the laws governing when the payment is "final").

# know mapping : MT103 = pacs.008

In the world of 2026 banking, "mapping" is the process of translating the old "telegraph-style" **MT103** into the modern "data-rich" **pacs.008**.

Since an MX message is much "larger" and more structured than an MT message, the mapping is rarely 1:1. It’s more like moving from a business card to a full LinkedIn profile.

---

### 1. The Core Mapping Table

Here is how a standard payment "evolves" from the old tag format into the new XML elements.

| MT103 Tag | Field Name | pacs.008 XML Path | Why it's different in 2026 |
| --- | --- | --- | --- |
| **:20:** | Sender's Reference | `InstrId` (Instruction ID) | Used only for the bank-to-bank leg. |
| **{3:UETR}** | Tracking ID | `UETR` | Now a **mandatory** element inside the XML. |
| **:32A:** | Value Date | `IntrBkSttlmDt` | Explicitly separated from the amount. |
| **:32A:** | Currency/Amount | `IntrBkSttlmAmt` | The "Interbank" amount. |
| **:50a:** | Ordering Customer | `Dbtr` (Debtor) | **Structured:** Name and Address are now separate tags. |
| **:52a:** | Ordering Institution | `DbtrAgt` | Identifies the sender's bank. |
| **:57a:** | Account With Inst. | `CdtrAgt` | Identifies the receiver's bank. |
| **:59a:** | Beneficiary | `Cdtr` (Creditor) | Includes the `/Acc` (IBAN) and structured name. |
| **:71A:** | Details of Charges | `ChrgBr` | Still maps to **OUR, SHA, or BEN**. |
| **:70:** | Remittance Info | `RmtInf` | Can be "Unstructured" (text) or "Structured" (invoice tags). |

---

### 2. The "Party" Deep-Dive (Tags 50 & 59)

This is the most critical part of the mapping for compliance. In MT, an address was just 4 lines of 35 characters. In MX (pacs.008), we use **Granular Mapping**:

**MT103 (Legacy):**

```text
:50K:/12345678
JOHN DOE
123 MAIN ST, APT 4
NEW YORK, NY 10001

```

**pacs.008 (ISO 20022 Mapping):**

```xml
<Dbtr>
    <Nm>John Doe</Nm>
    <PstlAdr>
        <StrtNm>Main St</StrtNm>
        <BldgNb>123</BldgNb>
        <PstCd>10001</PstCd>
        <TwnNm>New York</TwnNm>
        <Ctry>US</Ctry>
    </PstlAdr>
</Dbtr>

```

---

### 3. The "Ultimate Party" Mapping (The "Ghost" Fields)

MT103 was limited. If you paid someone *through* a third party, the data was often lost in the "Comment" tags (:70: or :72:). In pacs.008, we have dedicated fields that didn't exist in MT103:

* **Ultimate Debtor (`UltmtDbtr`):** If a parent company pays a bill on behalf of a subsidiary.
* **Ultimate Creditor (`UltmtCdtr`):** If the money is going to a final person who is not the direct account holder.

---

### 4. Why "Truncation" is a 2026 Headache

Because the industry is in a "Coexistence" phase, many banks use a **Translation Portal**.

* **Problem:** If you send a rich **pacs.008** with a detailed 500-character invoice list, but the receiving bank is still using an old **MT103** internal system, that system will "chop off" (truncate) the data to fit the old 140-character limit.
* **Result:** This often leads to "Sanctions Hits" or "Repair" fees because the critical data was lost in translation.

---

### Summary Checklist for Mapping

1. **Instruction ID** goes to `<InstrId>`.
2. **UETR** goes to `<UETR>`.
3. **Currency/Amount** goes to `<IntrBkSttlmAmt>`.
4. **Sender/Receiver** addresses must be broken into `<StrtNm>`, `<BldgNb>`, etc.
5. **Charges (OUR/SHA/BEN)** go to `<ChrgBr>`.

