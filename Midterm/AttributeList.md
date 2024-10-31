# Borrower

```
CWID: String (Unique ID for the teacher, e.g. "91234567")
Type: Enum (e.g., "Teacher", "Student")
State: Enum (e.g., "Active", "Suspended", "Blocked")
```

```
LibraryCard: LibraryCard Ptr (Reference to the current LibraryCard)
CheckedOutHistory: Collection (Collection to the history of CheckedOutRecord Ptr)
```

```
Fines: Float (Total fines owed by the Borrower)
Name: String (Name of the Borrower)
```

# LibraryCard
```
BarCode: String (Unique ID for LibraryCard, e.g., "T-91234567-001", "S-203948476-001")
Type: Enum (e.g., "Teacher", "Student")
State: Enum (e.g., "Active", "Expired", "Suspended")
```

```
Borrower: Borrower Ptr (Reference to Borrower)
CheckedOutRecords: Collection[4] (Collection to the current CheckedOutRecord Ptr, max concurrent count is 4)
```

```
ExpirationDate: Date (Expiration date of the LibraryCard)
RenewDate: Date (Renew date of the LibraryCard)
```

# Library
```
ID: String (Library unique ID, e.g., "DA-ML-001")
Type: Enum (e.g., "Library")
State: Enum (e.g., "Open", "Closed")
```

```
College: College Ptr (Reference to College)
Borrowers: Collection (Collection of Borrower)
Materials: Collection (All materials available in the library, including books and other resources)
LibraryCards: Collection (Collection of LibraryCards)
```

```
Name: String (Name of the Library)
Location: String (Location of the Library)
```

# Material (Catalog)
```
ID: String (Unique ID for Material, e.g. "BOOK-978-2-393-29387-5")
Type: Enum (e.g., "Book", "Newspaper", "DVD")
```

# Book (Subclass of Material)
```
ISBN: String (Unique ID for Book, e.g. "978-2-393-29387-5")
BookType: Enum (e.g., "Fiction", "Non-fiction")
State: Enum (e.g., "Available", "Unavailable")
```

```
Copies: Collection (List of BookCopy Ptr)
```

```
Title: String (Title of the Book)
Author: String (Author of the Book)
Publisher: String (Publisher of the Book)
Edition: String (Edition of the Book)
IsReferenceBook: Bool (Boolean to indicate is this a reference work or not)
LoanPeriod: Integer (Loan period for this Book, e.g.: 3 for reference book, 10 for others)
OverdueFine: Float (Overdue finem e.g.: 1 for reference book, 0.25 for others)
```

# BookCopy (or Copy)
```
BarCode: String (Unique ID for BookCopy, e.g. "BOOK-978-2-393-29387-5-001")
CopyType: Enum (e.g., "Hradback", "Paperback")
State: Enum (e.g., "Available", "CheckedOut", "Broken", "Lost")
```

```
CheckedOutRecord: CheckedOutRecord Ptr (Reference to the current CheckedOutRecord)
Book: Book Ptr (Reference to Book)
```

```
CatalogNumber: String (Catalog number for non-fiction materials, hardback/paperback might have different catalog #)
```

# CheckedOutRecord
```
ID: String (Unique ID for CheckedOutRecord)
Type: Enum (e.g., "Current", "History")
State: Enum (e.g., "Normal", "Overdue")
```

```
BookCopy: BookCopy Ptr (Reference to the BookCopy)
LibraryCard: LibraryCard Ptr (Reference to the LibraryCard)
```

```
DueDate: Date (Due date for returning the copy)
DateCheckedOut: Date (Date the copy was checked out)
DateReturned: Date (Date the copy was returned)
```
