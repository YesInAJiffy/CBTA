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

