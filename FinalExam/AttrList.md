# Company
```
CID: String (Unique ID for the Company, e.g. "CBD")
```

# Employee
```
EID: Integer    (Unique ID for the Employee, e.g. "0####")
Type: Enum      (e.g., "Clerical", "Programmer", "Salespeople", "SoftwareArchitect")
State: Enum     (e.g., "Active", "OnLeave", "Suspended", "Terminated", "Retired")
```

```
Name: String    (Name of Employee)
Address: String (Address of Employee)
```

## Clerical/Programmer/SoftwareArchitect
```
TimeLogs: Collection (Collection to the TimeLog)
```

```
AllowedHours: Integer (allowed hours of work per week, e.g. 60)
HourlyPayRate: Float (Hourly pay rate, exception for Salespeople) 
```

## Salespeople
```
Projects: Collection (Collection of Projects sold by this Salespeople)
```


# Customer
```
ID: String (Unique ID for Customer)
Catelog: Enum (e.g., "Manufacturing", "Retail", "Healthcare", etc.)
State: Enum (e.g., "Active", "Suspended", "Blocked")
```

```
Projects: Collection  (Collection of Projects own by this Customer)
```

```
Name: String (Name of the Customer)
Address: String (Address of the Customer)
VAT: String (VAT for the Customer)
```

# Project
```
InvoiceNumber: Integer (Unique ID for Project)
Type: Enum (e.g., "Overhead", "Normal")
State: Enum (e.g., "KickedOff", "Proposed", "Active", "Stopped", "Completed", "Insolvent", "Closed", "Archieved")
```

```
Customer: Customer Ptr (Ptr to Customer)
Programmers: Collection (Collection of approved Programmer)
WorkLogs: Collection (Collection of WorkLog)
```

```
Name: String (Name of the Project)
Contact: String (Contact info. on Customer side)
Budget: Float (Total budget)
CostToComplete: Float (Current budget)
```

# TimeLog
```
```

```
Employee: Employee Ptr (Ptr to Employee, can be Clerical, Programmer or SoftwareArchitect)
Project: Project Ptr (Ptr to Project)
```

```
TotalHours: Integer (Total work hours for the specific week)
Year: Integer       (TimeLog's year)
WeekOfYear: Integer (TimeLog's week of year)
```
