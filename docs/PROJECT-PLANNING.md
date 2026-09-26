# Forex Telegram Bot — Project Planning

> Living architecture and requirements document. This document records the decisions made during the planning phase and will be updated as new requirements are defined.

## 1. Project Purpose

The bot will provide a simple, multilingual Telegram interface for customers of the Forex service.

The initial scope includes:

- Customer onboarding through Telegram
- Multilingual user interface
- Simple and persistent navigation
- Customer information collection
- MetaTrader account information collection
- Social/contact information such as Instagram
- Location and other profile information
- Cryptocurrency deposits
- Payment tracking
- Automatic payment detection and confirmation where technically possible
- Administrative/manual override when automatic verification is unavailable or requires intervention

The architecture must be extensible so additional services, cryptocurrencies, customer fields, and workflows can be added without restructuring the entire application.

---

## 2. Supported Languages

The bot must support four languages from the beginning:

- English
- Spanish
- Arabic
- Persian

### Localization requirements

- The user's selected language must be stored in the database.
- Returning users should continue in their selected language.
- All customer-facing text, buttons, errors, notifications, and payment messages should use the localization system.
- Persian and Arabic require RTL-aware message and interface design.
- English and Spanish use LTR presentation.
- No business logic should depend directly on translated text.

Suggested structure:

```
src/localization/
├── en/
├── es/
├── ar/
└── fa/
```

---

## 3. Navigation and UX

The bot should be intentionally simple and easy to use.

### Main requirements

- Clear main menu
- Minimal number of steps for common actions
- Consistent button naming
- Ability to return to the main menu at any time
- A persistent **Start / Main Menu** action should remain available throughout the user journey
- Avoid exposing technical details to customers

Initial conceptual menu:

```
🏠 Main Menu

💰 Deposit
📋 My Information
📦 My Orders
🔎 Track Payment
🌐 Language
ℹ️ Help
```

The exact menu will be finalized after the complete customer workflow is defined.

---

## 4. Customer Information

A dedicated customer profile section will collect and manage information required by the Forex service.

Initial categories:

### Personal / General Information

Examples:

- Name
- Contact information
- Location
- Other business-required profile fields

### MetaTrader Information

The bot may collect fields such as:

- Platform: MT4 / MT5
- Account ID / Login
- Server
- Other account-related information required by the service

### Social Information

Example:

- Instagram ID / username

### Security requirement

Sensitive credentials must not be treated like ordinary profile data.

In particular, if a MetaTrader password is required, its storage, encryption, access permissions, logging policy, retention period, and deletion policy must be designed explicitly before implementation.

The bot must never expose sensitive credentials in normal user/admin logs.

---

## 5. Deposit System

The deposit section must support multiple cryptocurrencies rather than being designed only around Bitcoin.

Initial examples:

- Bitcoin (BTC)
- Tether (USDT)
- Additional cryptocurrencies to be defined

Conceptual flow:

```
💰 Deposit
    ↓
Select cryptocurrency
    ↓
Enter/select deposit amount
    ↓
Create payment/order
    ↓
Generate payment instructions
    ↓
Customer sends funds
    ↓
Detect transaction
    ↓
Verify transaction
    ↓
Confirm deposit
```

The payment architecture should use a provider abstraction so new currencies/providers can be added without changing Telegram handlers.

Suggested conceptual structure:

```
Payment Service
├── Bitcoin Provider
├── USDT Provider
├── Future Crypto Providers
└── Payment Verification
```

---

## 6. Payment Tracking

Every deposit should have a persistent status and a unique internal reference/order ID.

Initial payment lifecycle:

```
PENDING
    ↓
AWAITING_PAYMENT
    ↓
PAYMENT_DETECTED
    ↓
PAYMENT_VERIFICATION
    ↓
CONFIRMED
    ↓
COMPLETED
```

Possible exception states:

- EXPIRED
- CANCELLED
- FAILED
- MANUAL_REVIEW

The customer should be able to open a tracking section and see the current status of a deposit.

Example:

```
🔎 Track Payment

Order: #XXXXXX
Currency: BTC
Amount: 0.00 BTC

Status:
⏳ Waiting for payment
```

The exact statuses and transitions will be finalized after the complete business workflow is defined.

---

## 7. Automatic Payment Confirmation

Automatic confirmation is a core project goal.

Target architecture:

```
Customer
   ↓
Crypto Payment
   ↓
Blockchain / Payment Provider
   ↓
Transaction Detection
   ↓
Transaction Verification
   ↓
Confirmation Policy
   ↓
Deposit Confirmed
   ↓
Customer Notification
```

The system should verify relevant payment properties before confirming a deposit, such as:

- Correct network
- Correct asset/currency
- Correct destination/address
- Expected amount
- Transaction existence
- Required blockchain confirmations
- Transaction status
- Matching internal order/reference where technically available

### Manual override

Even with automatic confirmation, an administrative/manual override should exist for exceptional cases.

```
Automatic Verification
        +
Admin Review / Override
```

Automatic confirmation should not prevent an administrator from reviewing or correcting an exceptional payment.

---

## 8. Core Domain Model

The initial conceptual relationship is:

```
User
  ↓
Customer Profile
  ↓
Order / Deposit
  ↓
Payment
  ↓
Blockchain Transaction
```

Likely core entities:

- User
- CustomerProfile
- MetaTraderAccount
- Order
- Payment
- PaymentProvider
- BlockchainTransaction
- Notification
- AdminAction
- LocalizationPreference

The exact database schema will be designed after the remaining business requirements are collected.

---

## 9. Proposed Application Architecture

Initial application structure:

```
Telegram
   ↓
Bot / Router
   ↓
Handlers
   ├── Start / Menu
   ├── Profile
   ├── Deposit
   ├── Orders
   ├── Payment Tracking
   └── Support
          ↓
     Application Services
          ↓
   ┌──────┼───────────┐
   ↓      ↓           ↓
Database Payment    Notifications
        Service
          ↓
   Crypto Providers
```

Important architectural rule:

**Telegram handlers should not directly implement blockchain/payment-provider logic.**

Instead:

```
Telegram Handler
      ↓
Order Service
      ↓
Payment Service
      ↓
Payment Provider
      ↓
Database
```

This keeps the bot maintainable and makes provider changes safer.

---

## 10. Initial Repository Structure

The current planned structure is:

```
forex-telegram-bot/

├── src/
│   ├── bot/
│   │   ├── handlers/
│   │   │   ├── start/
│   │   │   ├── menu/
│   │   │   ├── deposit/
│   │   │   ├── profile/
│   │   │   ├── orders/
│   │   │   └── support/
│   │   │
│   │   ├── keyboards/
│   │   ├── middlewares/
│   │   ├── states/
│   │   └── filters/
│   │
│   ├── users/
│   ├── profiles/
│   ├── orders/
│   ├── payments/
│   │   ├── bitcoin/
│   │   ├── usdt/
│   │   └── providers/
│   │
│   ├── admin/
│   ├── notifications/
│   ├── localization/
│   │   ├── en/
│   │   ├── es/
│   │   ├── ar/
│   │   └── fa/
│   │
│   ├── database/
│   ├── services/
│   ├── config/
│   └── utils/
│
├── tests/
├── migrations/
├── scripts/
├── docs/
│
├── .env.example
├── .gitignore
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md
```

This is a planning structure, not yet a final implementation structure.

---

## 11. Initial Technology Direction

The initial technology direction discussed for the project:

- Python
- aiogram for Telegram Bot API integration
- PostgreSQL
- SQLAlchemy
- Alembic
- Docker
- VPS deployment with Docker as a later deployment target

Technology choices should be confirmed against the final requirements before implementation.

---

## 12. Important Architecture Principles

1. **Multilingual from day one**  
   Do not add localization after the bot is built.

2. **Payment-provider abstraction**  
   Do not couple business logic to a single cryptocurrency or provider.

3. **Persistent order/payment state**  
   Payment status must survive bot restarts and deployment changes.

4. **Automatic verification with manual fallback**  
   Automation is preferred, but exceptional cases must remain manageable.

5. **Security-first handling of credentials**  
   Sensitive MetaTrader information requires explicit security design.

6. **Simple customer UX**  
   Technical complexity belongs in backend services, not in the customer interface.

7. **Admin control**  
   Administrative actions and overrides must be auditable.

8. **Extensibility**  
   Future cryptocurrencies, services, fields, and workflows should be addable without major architectural changes.

---

## 13. Requirements Still To Be Defined

This document intentionally does not finalize the following items yet:

- Complete customer journey from /start to completion
- Exact services/products offered by the bot
- Exact deposit currencies
- Networks for each supported cryptocurrency
- Payment provider(s)
- Whether a unique address is generated for every order
- Required blockchain confirmations per asset/network
- Deposit amount rules and minimums
- Payment expiration rules
- Underpayment/overpayment handling
- Refund process
- Admin roles and permissions
- Admin interface
- Customer notifications
- MetaTrader credential requirements
- Exact profile fields
- Data retention/deletion rules
- Security/encryption strategy
- Logging and audit requirements
- Hosting/deployment details
- Backup and recovery strategy
- Rate limiting and anti-abuse measures

These will be added as the planning sessions continue.

---

## 14. Next Planning Phase

Before writing production code, the next session should define the complete business workflow.

Recommended sequence:

1. Define the exact customer journey
2. Define all main-menu sections
3. Define every customer input
4. Define deposit/order lifecycle
5. Define automatic payment verification
6. Define admin workflow
7. Define database entities and relationships
8. Define security requirements
9. Freeze the architecture
10. Begin implementation

**Current status: Planning / Requirements Discovery**

No production implementation is considered final until the remaining business requirements are defined.
