# Airline Ticket Booking Backend System


## Objective
- We need to build a backend feature for an airline company. our end-user is going to be someone who wants to book flights and query about flights, so we need a robust system to actually help them give the best experience possible.

- This Doc is going to solely focus on Backend Part. We want to prepare the whole backend keeping in the fact in mind that code-base should be easily maintainable as much as possible.

## Requirements
- A user should be able to search for flights from one place to another.
    - User should be able to mention the `src` and `dest` details.
    - User should be able to select the date of journey. _{V2 -> multicity and round trip implementation}_
    - User should be able to select the class of the flights. (Non-mandatory, have some default value)
    - User should be able to select the number of seats. (Non-mandatory, have some default value)
    - List down the flights based on the above data.
    - The best available flights should be shown based on price and least journey time.
    - Need to support pagination so that we can list chunk of flights at one point of time.
    - Filter of flights should be supported based on Price, Departure Time, Arrival time, Journey time, etc. _{V2 -> some more filters}_
- A user should be able to book a flight considering that user is reisterred on the platform.
    - Excess luggage addition feature should be supported.
- Tracking of the flight prices should be possible; user should be notified for any price drops or any delays. _{V2 -> some more notification service}_
- For booking, the user has to make a payment. `(dummy)`
- User should be able to list their previous and upcoming flights.
- User should be able to download their boarding pass if they have done `Web Check-in`.
- `Web Check-in` should be supported.
    - _{V2 -> Seat Selection feature}_
- Notification via email for `Web check-in`.
- Reqview system for users iff they have booked the flight.
    - Star based review system
    - Listing of flights should involve review display.
- User should be able to authenticate to our system using email and password.
- Cancellation of a flight should be supported and cancellation returns (dummy).
- While making a booking, a persone can reserve more than one seat with one login id.


## Non-Functional Requirements
- We can expect that we are going to have more number of flight searches than flight bookings.
- The system needs to be accurate in terms of booking.(**No Over booking**)
- _Expect that we will be having approx **1,00,000** total users, **5,00,000** bookings might happen in one quarter._
- So in one day we can expect _10,000_ bookings.
- System should be capable of scaling up to atleast 3x the current estimated traffic.
- The system should handle realtime updates to flight prices, before user makes the final booking.
- Concurrency should be handled, using RDBMS should be the good solution.


## Capacity Estimations
- **Storage Estimations**:
    - For upcoming 5 years, _80,00,000_ bookings, _2,00,000_ users.
    - Considering all the users records and booking records take _10 MB_ of data, then overall _10 TB_ of memory should be fine for out initial pilot run.
- **Traffic estimates**: If we consider 30:1 as the search:booking ratio, then max we can expect 1,50,000 search queries a day. _(2 queries/sec)_


## Authentication Service
URL: <https://github.com/Aditya16828/Authentication-Service-AirlineTicketBooking.git>

## Booking Service
URL: <https://github.com/Aditya16828/BookingService-AirlineTicketBooking.git>

## Email Service
URL: <https://github.com/Aditya16828/EmailService-AirlineTicketBooking>

## Flights Service
URL: <https://github.com/Aditya16828/FlightsService-AirlineTicketBooking>
