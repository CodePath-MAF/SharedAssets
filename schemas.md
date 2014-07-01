MVP Schemas
============

## Users
* ID - key identifer
* CreatedAt - time user is created
* Role - (Staff or User)
* Name
* Email
* Phone_Number
* Password
* CLA - Current Liquid Assets

## Transactions
* UserID - who does this transaction belong to?
* GoalID - what goal is this transaction apart of? if nil, not a goal transaction
* CreatedAt - time transaction added
* Amount - amount of the transaction can be +/-
* Description - what was the transaction?
* Type - Was this a debit or credit?
* Category - (Food, Supplies, Goal, etc)

## Goals
* UserID - which user is this goal associated with?
* Name - Simple Name of Goal
* Description - details of the goal
* Type - (Loan, Deposit, Vacation, etc)
* Status - (Achieved, In Progress)
* Amount - $ total of the goal
* TimeInterval - What interval was set for goal payments
* PaymentAmt - what was the payment amount chosen for this goal
* NumPayments - How many payments are needed to reach goal with interval and payment amount
* GoalDate - When do they wish to achieve this goal? (suggest # payments, payment amt, interval?)

Wanted Schemas
===============

## Staff
####(Assumed God Mode otherwise, ie can see all users)

* AccountsList - List of Users-IDs