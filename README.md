# Water Can Ledger

Create a clean, simple, professional web application called “Water Can Accounts” for a small 20-litre drinking-water can delivery business.

The application is primarily used by the business owner to replace his existing paper-and-card-based daily account entry. The UI must be extremely easy to operate, fast, and uncluttered. It should feel like a simple digital ledger, not a complex accounting or analytics platform.

Overall UI

Use a minimal, neat interface with:

Clean white/light background

Simple typography

Clear labels

Thin borders

Subtle rounded corners

One consistent accent color

Comfortable spacing

Responsive layout for desktop and mobile

Clear buttons and form controls

No background images

No decorative illustrations

No unnecessary animations

No graphs

No charts

No complicated dashboard

No excessive cards

No unnecessary financial/accounting terminology

The main navigation should contain only:

Daily Entry | Customers | History | Pending

1. Daily Entry

This is the primary screen and should be the fastest screen to use.

Display an Add Delivery form.

Fields:

Date

Automatically use today's date, but allow the user to change it.

Company

Provide a searchable company/customer field.

The companies are already stored in the system.

When the user types a few letters, show matching suggestions.

For example, typing:

Sri

should show:

Sri Lakshmi Hotel

Sri Vinayaga Stores

Sri Sakthi Traders

Sri Murugan Mess

The user selects the company instead of typing the complete name.

Number of Cans

Provide a quantity control:

− 10 +

Allow only whole numbers.

Do not allow:

letters

decimals

negative quantities

Rate per Can

Provide a dropdown containing only:

₹25

₹30

₹35

₹40

Each customer should have a saved default rate. When a customer is selected, automatically select that customer's usual rate.

The user must still be able to change the rate for a particular delivery.

Delivery Amount

Calculate automatically:

Number of cans × Rate per can

For example:

10 cans × ₹30 = ₹300

The user should not manually enter this amount.

Payment Received Now

Provide a separate optional field for money received during the same transaction.

For example:

Delivery: +₹300
Payment: −₹100
Pending: ₹200

The payment should be treated as a separate deduction, not as part of the delivery amount.

Save Entry

Provide a prominent Save Entry button.

After saving, clear the form and make it ready for the next customer.

2. Payment Entry

Provide a separate Record Payment function.

The business owner may receive money from customers at random times and in small amounts, so payments must be independent transactions.

Fields:

Date

Company search/select

Payment amount

Show:

Previous Pending
Payment
New Pending

Example:

Previous Pending: ₹2,450
Payment: −₹500
New Pending: ₹1,950

Provide a Save Payment button.

Never require the user to create a delivery entry simply to record a payment.

3. Customers

Create a simple customer list.

At the top provide:

Search company...

Display a straightforward table/list containing:

Company name

Contact person

Phone number

Current pending amount

View action

Provide:

+ Add Customer

Add Customer

Fields:

Company Name

Contact Person

Phone Number

Default Rate per Can

Opening Pending Amount

Optional Notes

The opening pending amount is important because the business may already have outstanding balances before using the application.

After creating a customer, that customer should immediately become available in the company search field.

4. Customer Details / Ledger

Clicking a customer should open that customer's complete account history.

Example:

ABC Hotel

Show prominently:

Current Pending: ₹2,450

Also display:

Contact person

Phone number

Default rate

Opening pending amount

Provide two quick actions:

+ Add Delivery

+ Add Payment

Then show a chronological transaction history.

Each transaction should display:

Date

Transaction type

Number of cans

Rate

Delivery amount

Payment

Running balance

Example:

05 Sep | Delivery | 10 cans | ₹30 | +₹300 | — | ₹2,450
05 Sep | Payment | — | — | — | −₹200 | ₹2,250
04 Sep | Delivery | 20 cans | ₹30 | +₹600 | — | ₹2,850

Every transaction should have an Edit option.

The running balance must be calculated from the transaction history rather than manually entered.

5. History

Create a simple transaction-history page.

Provide four filters:

Day | Week | Month | Custom

The user should be able to select a date or date range.

Display transactions in a clean table:

Date

Company

Cans

Rate

Delivery amount

Payment amount

For monthly viewing, show all relevant transactions for that month.

For weekly viewing, show all transactions within that week.

For daily viewing, show that day's transactions.

For custom viewing, allow the user to select a start and end date.

Do not use graphs or charts.

At the bottom, provide simple totals where useful:

Total Cans
Total Delivery Amount
Total Payments

6. Pending

Create a dedicated Pending Payments page.

Show only customers who currently owe money.

Display:

Company

Pending amount

Last payment date

Number of days since last payment

View action

Allow simple sorting such as:

Highest Pending

and

Oldest Pending

Clicking a customer should open their customer ledger.

Do not use graphs.

7. Accounting Logic

The application must treat deliveries and payments as separate transactions.

For every delivery:

Delivery amount = Number of cans × Rate

For the customer's account:

Current Pending = Opening Pending + Total Delivery Amount − Total Payments

Example:

Opening pending = ₹500
Delivery = ₹300
Payment = ₹100

Current pending:

₹500 + ₹300 − ₹100 = ₹700

A payment must never overwrite the previous pending amount.

Every delivery and every payment must remain in the transaction history.

8. Data Entry Rules

Enforce simple validation.

Number of cans

Numbers only

Whole numbers only

No negative numbers

No decimal values

Rate

Only:

₹25

₹30

₹35

₹40

Payment

Numbers only

No negative payment values

Company

A valid existing customer must be selected.

Prevent accidental duplicate customers where possible.

9. Editing Transactions

The owner must be able to correct mistakes.

For example, if he accidentally enters 50 cans instead of 5, he should be able to edit the transaction.

When a transaction is edited, automatically recalculate the customer's balance and all affected history.

Do not allow the user to manually change the calculated pending balance.

10. Optional Can Tracking

If the business needs to track reusable 20-litre cans, support:

Cans Delivered
Cans Returned
Cans Currently With Customer

Calculate:

Cans With Customer = Cans Delivered − Cans Returned

This should remain a secondary feature and must not make the main delivery-entry screen complicated.

11. Main Design Principle

The application should optimize for the business owner's real workflow:

Open application → Search customer → Enter cans → Confirm rate → Save

A normal delivery entry should require only a few actions.

Recording a payment should be equally fast:

Open payment → Search customer → Enter amount → Save

The application should replace the paper ledger without forcing the user to learn complicated accounting software.

Keep every page simple, clean, readable, and functional.

The priority is:

Speed → Accuracy → Easy history lookup → Clear pending amounts

not visual complexity.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/d00c706e-7cea-4975-9df2-4b4a442a365b).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
