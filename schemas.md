# Schema

## User
Extends the ParseUser object

**Property** | **Type** | **Notes**
--- | --- | ---
role | ParseRole obj | Staff or User
name | String
email | String
phoneNumber | String
password | String
totalCash | Number | Current Liquid Assets
setup | Boolean | is user set up? meaning, added initial cash amount.

## Transaction

**Property** | **Type** | **Notes**
--- | --- | ---
user | User obj | who does this transaction belong to?
goal | Goal obj | what goal is this transaction part of? if `null`, not a goal transaction
transactionDate | Date | date of the transaction
amount | Number | amount of the transaction can be +/-
name | String | what was the transaction?
type | Integer | Was this a debit or credit? enum [Debit = 1, Credit = 2]
category | Category obj | E.g: Food, Supplies, Goal, etc

## Goal

**Property** | **Type** | **Notes**
--- | --- | ---
user | User obj | which user is this goal associated with?
users | List of User Obj | Applicable to Lending Circle, list of users part of this Lending Circle
name | String | Simple Name of Goal
type | Integer | Goal Type: enum (Loan, Deposit, Vacation, etc)
status | Integer | Whats the status of the Goal? enum: [In Progress = 1, Achieved = 2]
amount | Number | total $ amount of the goal
paymentInterval | Integer | What interval was set for goal payments. Stored in days unit. enum: [Daily = 1, Weekly = 7, BiWeekly = 14, Monthly = 30, BiMonthly = 60]
paymentAmount | Number | what was the $ payment amount chosen for this goalDate
numPayments | Integer | How many payments are needed to reach goal with interval and payment amount
goalDate | Date | When do they wish to achieve this goal? (suggest # payments, payment amt, interval?)
numPaymentsMade | Integer | How many payments have been made for this goal
currentTotal | number | how much money has been paid thus far
parentGoal | Goal obj | `null` if goal does not belong to a Lending Circle group
cashOutDate | Date | Date when the user will receive its micro-credit. Only applicable to Lending Circle Goals.
paidOut | Boolean | is the Goal cashed out?

A Lending Circle Group is a special Goal

## Post

**Property** | **Type** | **Notes**
--- | --- | ---
user | User Obj | User that made the post
goal | Goal Object | Lending Circle Goal the post belongs to
content | String | The content of the message
type | Integer | type of post E.g [1: Message, 2: Event] (still in flux)
photo | Parse File | Photo attachment to the post

## Comment

**Property** | **Type** | **Notes**
--- | --- | ---
user | User Obj | User that created the comment
content | String | Content
post | Post Obj | Post that this comments belongs to


## Category (Utility)

**Property** | **Type** | **Notes**
--- | --- | ---
objectId | String | Object ID
name | String | Category name E.g: Fun, Food, Bills
color | String | Color representing the category (for app consistency)

Wanted Schemas
===============

## Staff (for polish)
####(Assumed God Mode otherwise, ie can see all users)

* accountsList - List of Users-IDs
