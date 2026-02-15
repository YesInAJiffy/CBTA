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

