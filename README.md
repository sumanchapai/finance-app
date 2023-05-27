# Planning

Components:

    - Users
    - Sets
    - Spendings
    - Earnings
    - Balances

## Users
    Permissions
    - Admin(togglable)

1. System starts with an admin user.
1. With the consensus of all admin, new users can be added.
1. With the consensus of all admin, the admin perssion of a user can be toggled.

## Sets
1. Any user can form a non-existing set. A set is a collection of users.

## Spendings
1. User can create a spending for a set on a particular date. The status of a
    spending is unapproved by default. The status chagnes to approved when number
    of approval for the spending = | S | - 1. A user cannot approve their own
    spending. 
1. Spending object has a certain amount (required), and bill report (required)
    associated to it. 
1. The author of a spending i.e. the expender can edit the spending. Once an
    edit is created, approval status associated to all users falls to UNAPPROVED
    meaning edit has to be approved by everyone in the group. Until an edit is
    approved, balances are based on last approved value. Newly created spendings
    don't show up in Balanced until approved by everyone in the Set.

## Earning
1. Earning has two users associated with it: the person who earns is called payee
    and the person who pays is called the payer. New/edited earnings won't be 
    reflected in the Balances report until approved by the payee.
1. When a user creates an earning, they are the payer. This is enforeced by the system
    and cannot change.
1. Fields that a payer can alter during creation/edit is only the amount
    (required) and payment receipt (optional).

## Balances
1. Balances concerns the view that is based on Earnings and Spendings models. It should
    in no way modify either of those data in the database. It may create its own records
    in the database and may display the data in whatever format it prefers.
