MVP Schemas
============

## Users
* id - key identifer
* createdAt - time user is created
* role - (Staff or User)
* name
* email
* phoneNumber
* password
* CLA - Current Liquid Assets

## Transactions
* userId - who does this transaction belong to?
* goalId - what goal is this transaction apart of? if nil, not a goal transaction
* createdAt - time transaction added
* amount - amount of the transaction can be +/-
* description - what was the transaction?
* type (integer) - Was this a debit or credit?
* categoryId - (Food, Supplies, Goal, etc)

## Goals
* userID - which user is this goal associated with?
* name - Simple Name of Goal
* description - details of the goal
* type (integer) - (Loan, Deposit, Vacation, etc)
* status (integer) - (Achieved, In Progress)
* amount - $ total of the goal
* timeInterval - What interval was set for goal payments
* paymentAmt - what was the payment amount chosen for this goal
* numPayments - How many payments are needed to reach goal with interval and payment amount
* goalDate - When do they wish to achieve this goal? (suggest # payments, payment amt, interval?)

## Categories (Utility)
* id
* name

Wanted Schemas
===============

## Staff (for polish)
####(Assumed God Mode otherwise, ie can see all users)

* accountsList - List of Users-IDs
