# Fed Protocols
When we talk about "US Fed Payments," we are referring to the **Federal Reserve Financial Services (FRFS)**. This is the infrastructure—often called "the plumbing"—that allows money to move between banks in the United States.

Just like the domains we discussed earlier, the Fed has different "rails" for different types of payments. Here is the breakdown of the major Fed payment systems:

---

## 1. The Core Payment Rails

The Federal Reserve operates three primary electronic systems, each designed for a specific speed and value.

| System | Best For... | Speed | Key Feature |
| --- | --- | --- | --- |
| **Fedwire®** | Multi-million dollar transfers (Wholesale). | Instant | High-value, critical, and irrevocable. |
| **FedACH®** | Payroll, tax refunds, recurring bills (Retail). | 1–3 Days | Batch-processed; very low cost. |
| **FedNow®** | Instant consumer & business payments. | Seconds | 24/7/365; the newest "Instant" rail. |

### Fedwire® (The "Big Money" Rail)

This is a **Real-Time Gross Settlement (RTGS)** system. It doesn't wait for a batch; it processes each transaction individually and immediately.

* **Usage:** Used by banks to settle large loans, corporate acquisitions, or real estate closings.
* **Risk Rule:** Because Fedwire is **irrevocable** (you can't "undo" a wire), the fraud scoring models for Fedwire are incredibly strict.

### FedACH® (The "Bulk" Rail)

The Automated Clearing House (ACH) is the workhorse of the US economy. It’s "Slow and Steady."

* **Batching:** Instead of sending 1,000 individual payments, a bank bundles them into one file and sends it to the Fed at specific times.
* **Example:** Your direct deposit paycheck or your monthly Netflix subscription.

---

## 2. FedNow®: The Newest Disruptor

Launched in **July 2023**, FedNow is the Fed's answer to modern demands for speed. Unlike the older rails, it never sleeps—it works on weekends and holidays.

* **Speed:** Settlement happens in less than 20 seconds.
* **The "Fraud Challenge":** Because the money moves instantly and cannot be reversed, FedNow requires much more advanced **ML Fraud Models** (like the ones we discussed) because there is no 2-day "waiting period" to catch a mistake.

[Image comparing FedACH batch processing vs FedNow instant settlement]

---

## 3. The National Settlement Service (NSS)

This is a "behind-the-scenes" rail. It allows private clearinghouses (like those that handle credit card checks) to settle their final balances using their Federal Reserve accounts. It's essentially the "Banker's Banker" service.

---

## How it relates to our earlier topics:

* **Fraud Scoring:** FedNow and Fedwire use the highest level of real-time scoring because the "Time-to-Fraud" is so short.
* **Bounded Context:** In a bank's software, the "Fedwire Domain" cares about liquidity and high-value limits, while the "FedACH Domain" cares about batch integrity and file formats (NACHA files).

### Summary of the "US Fed" Landscape

* **Fedwire:** For when it has to be there **now** and it's **expensive**.
* **FedACH:** For when it can wait until **tomorrow** and it's **cheap**.
* **FedNow:** For when it has to be there **now** and it's **2:00 AM on a Sunday**.

# UK Payment SYSTEM

In the UK, the payment landscape is divided into three main "rails," each serving a distinct purpose based on speed, value, and cost. Just like the US Fed systems, these are managed by central bodies (principally **Pay.UK** and the **Bank of England**).

---

## 1. The Three Primary Payment Rails

| System | Best For... | Speed | Key Feature |
| --- | --- | --- | --- |
| **Bacs** | Payroll, Direct Debits, bulk business runs. | 3 Working Days | Extremely low cost; handles huge volumes. |
| **Faster Payments** | Mobile banking, splitting bills, urgent invoices. | Seconds (24/7) | Near-instant; £1m limit (varies by bank). |
| **CHAPS** | House purchases, high-value corporate moves. | Same Day | Real-time settlement; no value limit. |

### Bacs (The "Bulk" Rail)

Bacs is the backbone of UK business. It operates on a fixed **3-day cycle**:

* **Day 1 (Input):** You submit your payment file to the system.
* **Day 2 (Processing):** Banks communicate and reconcile the funds.
* **Day 3 (Settlement):** Money leaves the sender's account and lands in the recipient's.

> **Common Use:** Over 90% of UK employees are paid via Bacs Direct Credit.

### Faster Payments (The "Retail" Rail)

Launched in 2008, this made the UK a global leader in instant payments. Unlike Bacs, it never sleeps—it runs on weekends and bank holidays.

* **Mechanism:** It uses a "Deferred Net Settlement" model, where the banks swap money instantly but "settle" the final balances with the Bank of England a few times a day.
* **Security:** This is the primary rail for **Confirmation of Payee (CoP)**, which checks that the name on the account matches the one you entered before you send the money.

### CHAPS (The "Wholesale" Rail)

CHAPS is the UK’s equivalent of Fedwire. It is a **Real-Time Gross Settlement (RTGS)** system managed directly by the Bank of England.

* **Usage:** Used for "Critical" payments where failure is not an option (like buying a home).
* **Cost:** While Bacs costs pennies, banks often charge £20–£30 for a CHAPS transfer.

---

## 2. The Infrastructure: Who Pulls the Levers?

The UK is currently undergoing a massive upgrade called the **Interbank Infrastructure Renewal (IIR)** (formerly known as the New Payments Architecture).

* **Pay.UK:** Operates Bacs and Faster Payments. They are currently working to move these systems onto a single, modern standard called **ISO 20022**.
* **Bank of England:** Directly operates the RTGS system and CHAPS.
* **The PSR (Payment Systems Regulator):** The watchdog that ensures these systems are competitive and fair.

---

## 3. Emerging Trends in 2026

* **Variable Recurring Payments (VRP):** Often called the "Direct Debit Killer." It uses Open Banking to allow you to set up recurring payments that are instant and easier to cancel or change than a traditional Bacs Direct Debit.
* **The Digital Pound:** The Bank of England is actively exploring a "Central Bank Digital Currency" (CBDC) to coexist with these existing rails.
* **Real-Time Fraud Prevention:** Because of the speed of Faster Payments, UK banks are now using **Agentic AI** and shared data networks to spot "Authorized Push Payment" (APP) fraud in real-time.

### Summary Comparison: UK vs US

| Feature | UK System | US Equivalent |
| --- | --- | --- |
| **Bulk/Payroll** | Bacs | FedACH |
| **High Value** | CHAPS | Fedwire |
| **Real-Time** | Faster Payments | FedNow / RTP |

# SWIFT Vs SEPA

While both systems move money across borders, they are fundamentally different: **SWIFT** is a global messaging network for any currency, whereas **SEPA** is a European harmonized "zone" for moving Euros specifically.

Think of **SWIFT** as a global postal service that can deliver any package to any country, while **SEPA** is a specialized, high-speed regional rail network designed only for one type of cargo (Euros).

---

## 1. SWIFT (Global & Multi-Currency)

SWIFT (Society for Worldwide Interbank Financial Telecommunication) doesn't actually "move" the money itself; it sends high-security instructions between banks.

* **Scope:** Global (200+ countries).
* **Currency:** Almost any currency (USD, GBP, JPY, etc.).
* **The "Correspondent" Chain:** If your bank doesn't have a direct relationship with the destination bank, the payment must pass through "Intermediary" banks. This is why SWIFT is often slower and more expensive.
* **Cost:** Higher. You often face "Sender Fees," "Intermediary Fees," and "Receiver Fees."

---

## 2. SEPA (European & Euro-Only)

SEPA (Single Euro Payments Area) was created by the EU to make a transfer from Paris to Berlin as easy and cheap as a domestic transfer.

* **Scope:** 36 countries (All EU members + UK, Switzerland, Norway, etc.).
* **Currency:** **Euro only.** Even if you send from a GBP account in London, it must be converted to EUR to travel over the SEPA rail.
* **The "Domestic" Feel:** By law, banks cannot charge more for a SEPA transfer than they do for a local transfer.
* **SEPA Instant:** A modern sub-type that settles funds in **under 10 seconds**, 24/7/365.

---

## 3. Comparison at a Glance (2026)

| Feature | SEPA | SWIFT |
| --- | --- | --- |
| **Geographic Reach** | Europe (36 countries) | Global (200+ countries) |
| **Currency** | **Euro (EUR) Only** | Multi-currency (150+) |
| **Speed** | 1 business day (Instant = 10 sec) | 1–5 business days |
| **Typical Cost** | €0 to €1 | $15 to $50+ |
| **ID Required** | IBAN only | IBAN + BIC (SWIFT Code) |

---

## Which one should you use?

* **Use SEPA if:** You are sending Euros to someone in a participating European country (e.g., paying a French supplier from a UK business account).
* **Use SWIFT if:** You are sending money anywhere outside Europe, or if you need to send a specific currency like USD to a bank in Germany.

> **Pro Tip:** In 2026, many FinTechs use "Shadow Routing." If you send money globally, they might use SEPA for the European leg of the journey and then switch to a local rail in the destination country to avoid expensive SWIFT fees.

# Real Time Payments

In 2026, **Real-Time Payments (RTP)** are no longer a "luxury" feature—they have become the global standard for how money moves. While traditional systems like ACH are like sending a letter, RTP is like sending an instant message: the money is sent, cleared, and settled in seconds, 24/7/365.

---

## 1. What Makes a Payment "True" Real-Time?

There is a common misconception that apps like Venmo or PayPal are real-time. While they *feel* instant, they are often "Closed Loop" systems (the balance updates in the app, but the actual bank-to-bank money move takes days).

A **True RTP** system has four key characteristics:

* **Instant Availability:** The recipient can spend the money within seconds.
* **Immediate Settlement:** The banks exchange the actual value behind the scenes instantly (no "IOUs").
* **Irrevocability:** Once sent, the payment cannot be reversed. This is why fraud detection must be proactive.
* **24/7 Operations:** It works at 3:00 AM on Christmas Day just as well as 10:00 AM on a Tuesday.

---

## 2. The Global RTP Map (2026)

Different countries have built their own "Instant Rails." By 2026, over 80 countries have live RTP schemes.

| Region | System Name | Why it’s Famous |
| --- | --- | --- |
| **India** | **UPI** | The world leader. It uses "Virtual Payment Addresses" (like an email) instead of bank account numbers. |
| **Brazil** | **Pix** | Massive adoption; it practically replaced cash for street vendors and large businesses alike. |
| **USA** | **FedNow & RTP®** | The US finally caught up. FedNow (Federal Reserve) and RTP (The Clearing House) now compete for instant dominance. |
| **UK** | **Faster Payments** | One of the oldest systems, now being upgraded to the "New Payments Architecture." |
| **EU** | **SEPA Instant** | Mandated across the Eurozone to ensure all banks offer instant transfers by default. |

---

## 3. The Infrastructure: ISO 20022

The secret language that makes 2026 RTP work is **ISO 20022**. Unlike old systems that only sent a name and an amount, this new standard allows "Rich Data" to travel with the money.

* **Example:** A business can send an invoice, a breakdown of taxes, and a discount code all inside the same payment message. This makes **reconciliation** (matching payments to bills) automatic.

---

## 4. The "Dark Side": Real-Time Fraud

The biggest challenge in 2026 is that **faster payments mean faster fraud**. Because RTP is irrevocable, scammers love it.

* **APP Fraud (Authorized Push Payment):** Scammers trick you into *willingly* sending them money (e.g., "This is your bank, move your money to a 'Safe Account' now").
* **The Solution:** Banks now use **Agentic AI**—AI agents that scan the "Rich Data" of a transaction in milliseconds to spot patterns of social engineering before you hit "Confirm."

---

## Summary: RTP Use Cases

* **Gig Economy:** Uber drivers or freelancers getting paid the second the job is done.
* **Emergency Insurance:** Receiving a claim payout while standing in your flooded kitchen, not 5 days later.
* **Just-in-Time Logistics:** A truck driver’s payment clearing instantly so they can be released from a loading dock.

