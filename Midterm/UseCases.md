# Transactions

## Add a new purchased copy of a book to the library's current inventory.
```
Library verify the required path "Material > Book" exists
Create one if not
```
From ESD "Copy"
> Start
>> Add() event

## Remove an existing copy from the inventory due to damage or loss.
From ESD "Copy"
>> YouAreBroken() event

## Issue a new card to borrower
```
Library verify the Borrower's indentity through College
Library check the Borrower isn't current in the Library.Borrowers collection
```
From ESD "LibraryCard"
> Start
>> Register() event


## Borrower pays all or part of their outstanding fines
From ESD "LibraryCard"
> PayFine() event
>> change state from Suspended to Active or Expired


## A specific borrower attempts to check out a specific copy.
```

```

## A specific copy is returned
## New day

# Reports

1. Overdue: For each borrower with overdue material, return
   Borrower: Name, "type of borrower" and library card barcode number
   For each overdue Item held by that borrower:
   Title, author, bar code, date checked out, and amount currently owed
2. Inventory: For each book in the library inventory, return:
   Title, author, type, ISBN #, catalog # (if applicable)
   For each copy:
   Status
   If checked out:
    Date checked out
    Date due back
    Amount owed (if any)
    Borrower name, type and card #

# Queries

1. Return all information on a borrower (see above), given the library card bar code #
2. Return all information on a copy (see above), given the copy bar code #
3. Return all information on a book, given the book ISBN
