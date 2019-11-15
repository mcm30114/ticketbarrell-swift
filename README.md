# ticketbarrell-swift
an exercise to emulate the "raffle ticket" experience from ticket selling, winner pulling, interactions between the event sponsor and the participants.

## Example Scenario:

A person goes to a social event. As part of the social event, a drawing will be held to award prizes.  At the event, the Person (**TICKET-HOLDER**) obtains (buys, is given) one or more tickets from a **TICKET-ATTENDANT**.  These tickets are typcially on a paper roll (**TICKET-ROLL**) and each **TICKET** has two sections to it -- an "upper part" and a "lower part".  On both parts, the same sequence number is printed.  When the **TICKET-ATTENDANT** provides the sequential **TICKET** to the **TICKET-HOLDER**, the **TICKET-HOLDER** gets the two part ticket, puts some identifier (name, phone number, email, etc) on one part of the **TICKET** and deposits that written on **TICKET** into a **TICKET-BARRELL**.  The **TICKET-HOLDER** then keeps the opposite half of the **TICKET** until the **TICKET-PULL** event happens. 

At the **TICKET-PULL** event, the **TICKET-ATTENDANT** will reach into the **TICKET-BARRELL** and randomly pull a **TICKET** out of the barrell can then call out the sequence number.  If the **TICKET-HOLDER** is present, they identify (usually YELL OUT) that they have the matching **TICKET** half, present it to the **TICKET-ATTENDANT** for verification, and if there is a match, the prize is then awarded to the **TICKET-HOLDER**.  The winning **TICKET** is usually then collected and destroyed.  The next **TICKET-PULL** event starts, and this process repeats until all awards or prizes are given out. 

Some permutations to the **TICKET-PULL** Event:
1) The **TICKET-HOLDER** must be present to win (or not).
2) If the called **TICKET** is not redeemed, it can be returned to the barrell (or not)
3) **TICKET-ROLL** can have a finite number of tickets available (or not)
4) Tickets can be sold up to a particular "Closing time"
5) Tickets cannot be purchased after the end of the **TICKET-PULL** event
6) Tickets cannot be purchased after the **NUMBER-OF-TICKETS** are exhausted

## General Actors

**TICKET-ROLL** -- Source of all tickets.  Sequence number can start at a particular number (Long INT) and have **NUMBER-OF-TICKETS** (Long INT) as the count of tickets available on the roll. **TICKET** numbers are sequential positive integers.

### METHODS
- set up ticket roll
- pull a ticket
- status of ticket roll



### INSTANCE VARIABLES
- number of tickets in roll
- 


**TICKET-BARRELL** -- container of all **TICKETS** taken from a **TICKET-ROLL** for the purposes of that specific **EVENT**.

### METHODS
- hold tickets for drawing



**TICKET-PULL** -- One instance of an event.

### METHODS
- draw ticket

### INSTANCE VARIABLES
- number of tickets to pull


**EVENT** -- A period of time where the process of the **TICKET-PULL** will be valid. There is usually a period where the tickets can be obtained ((**TICKET-PULL-OFFERING-START-DATE-TIME**) and ends (**TICKET-PULL-OFFERING-END-DATE-TIME**)) , the time of the event 

### METHODS
- set start and end time of selling tickets
- set start and end time of ticket pull
- set start and end time of winning ticket claims


**TICKET** -- an instance of a ticket. A **TICKET** has 2 parts to it, one part stays with the event and is put into the **TICKET-BARRELL**. The other half is given to the **TICKET-HOLDER**.

### METHODS
- identifable unique number

**TICKET-HOLDER** -- an event attendee who wishes to participate in the **EVENT**.  A **TICKET-HOLDER** can have one or more tickets, limited only to the amount of tickets left on the **TICKET-ROLL**. A **TICKET-HOLDER** has an identification (number, hash, ID, etc) similar to a limited profile. No PII information should be stored.


### METHODS
- check pulled tickets
- ckeck tickets for winning status
- buy tickets
- delete tickets

**TICKET-ATTENDANT** -- The agent that controls the flow of the **TICKET-PULL** event 

### METHODS
- call out for event
- check validity of winning claim

