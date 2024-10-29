# Borrower (Abstract Class)

```
CWID: String (Unique identifier for the teacher, e.g. 91234567)
Type: Enum (e.g., "Teacher", "Student")
State: Enum (e.g., "Active", "Suspended", "Blocked")
```

```
LibraryCard: LibraryCard Ptr (Reference to the current LibraryCard)
CheckedOutRecords: Collection (Collection to the current CheckedOutRecord Ptr)
CheckedOutHistory: Collection (Collection to the history of CheckedOutRecord Ptr)
```

```
Fines: Float (Total fines owed by the borrower)
```

## Teacher (Subclass of Borrower)
```
Status: Enum (e.g., "Employed", "Unemployed", "On Leave")
```

## Student (Subclass of Borrower)
```
Status: Enum (e.g., "Full-time", "Part-time", "Not Enrolled") 
```

# LibraryCard
```
Unique ID: String (Barcode, e.g., "1123432E")
Type: Enum (e.g., "Library Card")
State: Enum (e.g., "Active", "Expired", "Suspended")
```

```
Borrower: Borrower Ptr (Reference to Borrower)
```

```
ExpirationDate: Date (Expiration date of the LibraryCard)
IsExpired: Boolean (Indicates whether the LibraryCard expired)
```

# Library
```
Unique ID: String (Library ID, e.g., "ML001")
Type: Enum (e.g., "Library")
State: Enum (e.g., "Open", "Closed")
```

```
College: College Ptr (Reference to College)
Borrowers: Collection (List of borrowers with valid library cards)
Materials: Collection (All materials available in the library, including books and other resources)
```

```
Name: String (Name of the Library)
Location: String (Location of the Library)
```

# Material (Catalog)
```
ID: String (Unique for materials)
Type: Enum (e.g., "Book", "Newspaper", "DVD")
```

# Book (Subclass of Material)
```
ISBN: String (Unique ID for book)
Type: Enum (e.g., "Fiction", "Non-fiction")
State: Enum (e.g., "Available", "Unavailable")
```

```
Copies: Collection (List of Copy Ptr)
```

```
Title: String (Title of the Book)
Author: String (Author of the Book)
Publisher: String (Publisher of the Book)
Edition: String (Edition of the Book)
IsReferenceBook: Bool (Boolean to indicate is this a reference work or not)
```

# Copy
```
Unique ID: String (Barcode)
Type: Enum (e.g., "Hradback", "Paperback")
State: Enum (e.g., "Available", "CheckedOut", "Broken", "Lost")
```

```
CheckedOutRecord: CheckedOutRecord Ptr (Reference to the current CheckedOutRecord)
```

```
CatalogNumber: String (Catalog number for non-fiction materials)
```

# CheckedOutRecord
```
Unique ID: String (Copy Barcode + LibraryCard Barcode + xx )
Type: Enum (e.g., "Current", "History")
State: Enum (e.g., "Normal", "Overdue")
```

```
Copy: Copy Ptr (Reference to the Copy)
LibraryCard: LibraryCard Ptr (Reference to the LibraryCard)
```

```
DueDate: Date (Due date for returning the copy)
DateCheckedOut: Date (Date the copy was checked out)
DateReturned: Date (Date the copy was returned)
```


# Remaining questions
