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

