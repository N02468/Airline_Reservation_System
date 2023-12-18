# Airline_Reservation_System
Table of Content

Introduction .............................................................................2
System Objectives...................................................................2
System Context.......................................................................4
Functional Requirements ...................................................... 5

Airlines Reservation

2

Airlines Reservation

3

Introduction

The project is to design an airline reservation system that will take care of all the reservation
related issues and will give the result in quick time.

System Objectives

1.1 The Airline Reservation System (ARS) is a software application to assist an airline
with transactions related to making ticket reservations, which includes blocking,
reserving, canceling and rescheduling tickets.
1.2 From the viewpoint of the airlines -
1.2.1 Minimize repetitive work done by the system administrator and reservation clerks.
1.2.2 The users should be basically taken through the same steps by the system as they go
through in conventional desk-reservation systems.
1.2.3 Maintain customer information in case of emergency, e.g. flight cancellation due to
inclement weather. The profile can also be used by the airline company to track user
preferences and travel patterns to serve them better, plan routes, for better marketing
and efficient scheduling of flights.
1.2.4 Maximize the revenue of the airline company by various means:
1.2.4.1 Increase awareness among frequent travelers about various special offers and
discounts.
1.2.4.2 Minimize the number of vacant seats on a flight and maximize flight capacity
utilization.
1.2.4.3 Maintain the capability to adopt a flexible pricing policy. The price of the tickets
should be dynamically determined based on how early, before the date of departure,
the customer buys the ticket.
1.3 A survey conducted by airline companies shows that users of an existing reservation
system would respond favorably to an ARS that satisfied or helped them satisfy the
following objectives:

Airlines Reservation

4
1.3.1 Reduce effort and frustration for travelers in scheduling a trip, especially by reducing
the search effort for the flight they need to take.
1.3.2 Show all possible combinations and itineraries available for a pair of origin-destination
cities.

1.3.3 Reduce redundancy in the information required from the customers in order for them
to buy tickets, create user accounts etc.
1.3.4 Check the validity of input data and give a feedback to the user in case of errors or
inconsistency.
1.3.5 Make it easy for travelers to check the ticket status or make changes to their trip.

Airlines Reservation

5

2. System Context

2.1 The ARS will provide the following types of easy-to-use, interactive, and intuitive
graphical and telephonic interfaces.
2.1.1 The ARS will provide an easy-to-use, intuitive Graphical User Interface (GUI) as part
of the Clerk/Administrator’s working desktop environment.
2.1.2 The ARS will also provide an interactive GUI, on the World Wide Web for the general
customers.
2.1.3 The above two ARS interfaces shall help provide the following functionalities to the
users - access to the ARS to check the flight schedule, availability of seats, ticket price
and to block, reserve, cancel, and reschedule tickets.

Airlines Reservation

6

Proposed Solution
A system needs to be developed based on following requirements:

Functional Requirements
3.1 User Accounts
3.1.1 The passenger, who will henceforth be called the ‘user’, will be presented with 3
choices by the reservation system, as the first step in the interaction between them. A user can
choose one of these and his choice would be governed by whether he is a guest or a registered
user and whether he wants to check the availability of tickets or also block/buy them. The
terms ‘registered user’ and ‘guest’ are described below.
3.1.1.1 A user who has traveled by the airline earlier would have been given a user id and a
password. He would have his personal information stored in the database referred to as ‘DB-
user’. This ‘personal information’ would be henceforth referred to as ‘profile’. Such a user
with a profile in DB-user shall be called a ‘registered user’. A registered user will be able to
check the availability of tickets as well as block/buy a ticket by logging into the system.
3.1.1.2 A new user, on the other hand, would either have to
a) register himself with the system by providing personal information or
b) log into the system as a guest.
In case of ‘a’, the new user becomes a registered user.
In case of ‘b’, the new user would remain a guest.
A guest can only check the availability of tickets and cannot block or buy tickets.
But a registered user can also act as a guest if he only wants to check the availability
of tickets. ‘Availability of tickets’ always refers to viewing the flight schedule for
given days, the price of tickets and any discount offers. The system shall present the
user with an option to exit from the system at any time during the following processes.

3.2 Registration and creation of user profile
The system shall require a user to register, in order to carry out any transactions with it
except for checking the availability of tickets. It will ask the user for the following
information at the least – a user id, a password, first name, last name, address, phone

Airlines Reservation

7
number, email address, sex, age, preferred credit card number. The system will
automatically create a ‘sky miles’ field and initialize it to zero in the user’s profile.

3.3 Checking Availability
3.3.1 After logging in a user (either a registered user or a guest), the system shall request
him to enter the following details – origin city and destination city. “City’ is a generic
term and refers to a city or town as the case may be. The origin and destination cities
would be entered as text.
3.3.2 The system shall now refer to the flight schedule database and check if there is any
ambiguity with the names of the cities. In case there are more than two cities with
same name as entered by the user, the system shall list all of them (with more
qualifications) and ask the user to select one of them. In case, either the origin or
destination cities are not listed as being directly serviced by the airline, the system
shall suggest the nearest city to which service is available, including the distance of the
destination city from this nearest city.
3.3.3 After the origin and destination cities are ascertained, the system shall now access the
flight schedule database and checks if there is a direct operational service between the
two cities. If not, the system shall suggest possible routes and transfer points using a
‘route selection algorithm’. The user shall now be presented with a choice of either
selecting one of the routes. In case he selects a route, the system shall fill in the
intermediate stop over points and create a multiple trip itinerary for the user.
3.3.4 The system shall now ask the user to enter the following details - class, one-way or
round trip, departure date and the number of adult passengers, children and senior
citizens.
3.3.4.1 ‘Class’ refers to business class/first class/club class/smoking/non smoking. This choice
shall be made by the user through a drop down menu indicating all the possible
combinations of choices.
3.3.4.2 One-way/round trip shall be either a drop down menu or a check box selection.
‘Departure date’ refers to either a single date or a range of dates, entered through a
calendar-like menu. This menu shall not show dates in the past or those dates that are
too ahead in the future(as determined by the airline policy). In case, the trip is a round
trip, the system shall also ask the user to enter the departure date on the return trip.

Airlines Reservation

8
3.3.4.3 Having taken all the above input from the user, the system checks for any false entries
like the departure date on the return trip being earlier than the departure date on the
onward trip. In case of incompatibility, the system shall display a suitable error
message and prompt the user to enter the information correctly.
3.3.5 Having taken all of the information as laid out above in 3.3.1 and 3.3.4, the system
shall now access the flight schedule database and queries it using the input provided
by the user.
3.3.6 The system queries the reservation database to check which of the flights on the
schedule have seats available. The system displays the results in a suitable form (a
tabular form) with the following information depicted – for each flight number – the
flight number, departure time in origin city, arrival time in destination city, the
duration of the flight (taking into account the possibility of a change of time zone) and
the number of seats available on that flight.
3.3.6.1 There can be several flights between two cities and all of them will be listed for the
particular date that the user wants to depart from the Origin City. In case, the user has
entered a range of dates, the system shall display all the flights for all those dates in
the range.
3.3.6.2 If the user has requested a round trip, the system shall display two tables - one for the
onward trip and one for the return trip. There will be a check box in front of each line
in the table representing a flight with available seats.
3.3.6.3 The user is now asked to check one of the boxes reflecting a choice of a flight number
and time. In case of a round trip, the user is asked to check one box each in the two
tables.
3.3.7 The system shall now display the price of the ticket for the trip. This will be the sum of
the prices for all the members of the travel party being represented by the user.
3.3.7.1 The system shall also list any rules regarding the cancellation of tickets – what
percentage of the price will be refunded within what date ranges. This will be
displayed as a table.
3.4 Making Reservations/Blocking/Confirmation
3.4.1 After having taken the user through the step 3.3, Checking Availability, The system will
now ask the user if he wishes to block/buy the ticket. If yes, and
a) if the user has been a guest, he will have to first register and become a registered user
and then log onto the system.

Airlines Reservation

9
b) If the user is already a registered user, and if he has logged on already, he can
block/buy the ticket, but if he has been acting as a guest, he will have to log on.
3.4.2 Having ensured that the user is logged on validly according to 3.4.1, the system
compares the departure date with the system date. If the departure date falls within 2
weeks of the system date, the system informs the user that he has no option to block
the ticket and asks him if he would like to buy it.
3.4.2.1 If the difference between the departure date and system date is more than 2 weeks, the
system asks the user if he would like to block or buy the ticket. The system informs
the user that he can block the ticket at no cost now. It also informs him that if he
chooses to block the ticket, he should make a final decision before 2 weeks of the
departure date. The system shall send an email to the user, 3 weeks before the
departure date as a reminder, in case he decides to block the ticket now.
3.4.3 Having taken the input from the user in 3.4.2, the system shall now proceed to update
the reservation database It will decrement the number of available seats on the
particular flight for the particular class by the number of travelers being represented by
the user.
3.4.3.1 In case of a blocking, the system makes a note of it in the database - to be used if the
user doesn’t turn up before 2 weeks of the departure date. It generates a blocking
number and displays it for the user to note down.
3.4.3.2 In case the user buys the ticket, the system accesses his profile and charges the price of
the ticket to his credit card number. It simultaneously generates a confirmation number
and displays it to the user for him to note down. The ticket has been reserved.
3.4.3.3 It adds the mileage of the trip (accounting for the number of travelers) to the skymiles
in his profile.

3.5 Confirm Ticket
3.5.1 A user who has earlier blocked a ticket after going through the steps 3.2 through 3.4, is
required to either confirm the ticket before two weeks of the departure date or the
ticket stands cancelled.
3.5.2 To let the user confirm a ticket, the system shall first log him on and ask for his
blocking number. Then it accesses database and removes the check mark, which so far
represented a blocked seat. The seat is now confirmed and reserved for the user.

Airlines Reservation

10
3.5.3 The system accesses database and charges the price of the ticket to the credit card
number of the user. It simultaneously generates a confirmation number and displays it
for the user to note down. The ticket has been reserved.
3.5.4 It adds the mileage of the trip (accounting for the number of travelers) to the skymiles
in his profile.

3.6 Reschedule Ticket
3.6.1 The system shall present the user with an option to re-schedule his travel party’s trip.
In order to do this, the system first logs on the user and requests his confirmation
number. It will not allow a user to reschedule a blocked ticket but only a confirmed
ticket. Using this, it queries database-reservation and presents the details of the trip to
the user, including but not limited to origin city, destination city, date of departure and
date of arrival (in case the trip is a round trip).
3.6.2 The system shall now ask the user to select new dates from the calendar-menu. It now
goes through step 3.3.
3.6.2.1 In case, there are no available tickets for the dates entered, it displays a suitable
message informing him that rescheduling to that date is not possible.
3.6.2.2 In case there are tickets available, the system asks the user to select the flight number
for the trip (another for the return trip if the trip is a round trip) and proceeds to update
the database.
3.6.3 The system accesses database and decrements the number of available seats on the
flight(s) by the number of members in the user’s travel party. It then increments the
entry for the previous flight by the same number to reflect an increase in the available
seats on it as a result of the rescheduling.
3.6.4 The system now checks if there is any difference in the prices of the tickets. If so, it
accesses database and charges or credits the credit card as the case may be. The system
generates a new confirmation number and displays it to the user.

3.7 Cancellation

Airlines Reservation

11
3.7.1 The system shall also give the user an option to cancel a confirmed ticket or a blocked
ticket.
3.7.1.1 The latter case is simpler and will be dealt with first – the system shall first log on the
user and request the blocking number. Then it accesses dataabase and updates it by
incrementing the number of available seats by the number of people in the user’s
travel party.
3.7.1.2 In the former case, i.e., for a confirmed ticket, it asks for the confirmation number and
accesses database and presents the details of the trip as in step 3.6.1.
3.7.2 It then lists the applicable rules for cancellation of tickets and depending on the system
date and the departure date, it displays the % of the amount that would be refunded if
the user cancels the ticket.
3.7.3 After the user cancels the ticket, the system generates a cancellation number and
displays it for the user to note down. It accesses reservation database and updates it by
incrementing the number of available seats on that flight by the number of travelers in
the user’s party. It accesses user database and credits the refund amount to his credit
card number. The system then deducts the mileage of the trip (taking into account the
number of travelers in his party) from the sky miles in his profile.

3.8 Update Profile
The system shall enable the user to update his profile at any time. Changes can be
made in fields including but not limited to address, phone number and preferred credit
card number.

3.9 View Ticket Status
The system shall allow a user to view all information about his trip. After logging him
on, it asks for his blocking number or his confirmation number. It accesses database-
reservation and retrieves the details of the trip and presents them to the user in a
convenient format, including any last minute changes to the flight timings etc. Such
changes will be highlighted.

3.10 Query Flight Details

Airlines Reservation

12
The system shall allow any user (registered or non registered) to access the details
about the arrival and departure times of a flight by requesting the user to input the
flight number and date. The system accesses database-schedule and presents the time
of arrival and departure.
