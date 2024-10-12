# Part 0 - CCD

## Complete Request Fulfilment

![CCD0](./images/FBN-CCD0.png)

## Complete Resource Provisioning

![CCD1](./images/FBN-CCD1.png)

# Part 1 - Vocabulary

## Candidates for the associated object

```
(C) Class – Basic application abstraction (like “Teacher” is a Class)
(SC) Subclass – is a subclass of a more general class (like “PartTime” is a subclass of Teacher)
(CC) Collection Class – Collects a specified class of objects (like “Faculty” is a Dept. collection class of
Teacher)
(OO) Object of – Not a class at all, but an object of a class (like “De Anza” is an object of the College class)
(E) Event – is an event (function or method) of a class (like “Enroll” is an event of Student)
(A) Attribute – is an attribute of a class (like “GPA” is an attribute of Student)
(TV) Type Value – is a possible “type” of a class (like “Foreign” is a type of Student)
(SV) State Value – is a possible state of a class (like “Full” is a state of a Section)
(ID) Unique ID – Uniquely identifies a specific object (like “StudentNum” identifies a specific Student)
(NR) Not Required – may be duplicate of another abstraction or simply not make sense
```

## "things" ⇔ associated object
| things            | associated object |
| ----------------- | ----------------- |
| Airport           | (C) |
| ArrivingAirport   | (A) of a Route class  |
| Boeing747         | (TV) of a PlaneModel  |
| Gate              | (C) |
| AssignedGate      | (A) of a FlightInstance  |
| BagTag            | (A) of a Seat  |
| BarCode           | (A) of a Seat  |
| CheckIn           | (E) of a Ticket  |
| CheckedIn         | (A) of a Ticket  |
| Plane             | (C)  |
| Model             | (C)  |
| OnTime            | (SV) of a FlightInstance  |
| ScheduledTA       | (A) of a Flight  |
| EstimatedTA       | (A) of a Flight  |
| ActualTA          | (A) of a FlightInstance  |
| Reservation       | (C)  |
| BusinessClass     | (TV) of a Seat |
| RoundTrip         | (A) of a Reservation  |
| FrequentFlyer     | (A) of a Passenger  |
| Flight            | (C)  |
| FlightInstance    | (C)  |
| Weather           | (A) of a Airport  |
| TSA #             | (A) of a Ticket  |
| Hijacker          | (NR)  |
| MaxRange          |   |
| MilesTillEmpty    | (A) of a FlightInstance  |
| Meal              | (A) of a Seat  |
| SeatChart         | (A) of a Plane |
| SeatMap           | (A) of a Plane Model |
| Receipt           | (A) of a Reservation  |
| Price             | (A) of a Ticket  |
| SFO               | (OO) of a Airport  |
| CoPilot           | (SC) of Pilot  |
| Delayed           | (SV) of a FlightInstance  |
| Luggage           | (A) of a Seat  |
| Tag               |   |


# Part 2 - Attribute Lists

## Plane

```
                             // The big 3
ID (String);                 // Unique ID of Plane ()
Type (enum);                 // Type of Plane ("xxx"/"xxx")
State (enum);                // State of Plane ("xxx"/"xxx")

                             // The connections to other classes (from the CCD)


                             // Other stuff that may be necessary
```

## Flight Instance

```
                             // The big 3
ID (String);                 // Unique ID of Flight ()
Type (enum);                 // Type of Flight ("xxx"/"xxx")
State (enum);                // State of Flight ("xxx"/"xxx")

                             // The connections to other classes (from the CCD)


                             // Other stuff that may be necessary
```
