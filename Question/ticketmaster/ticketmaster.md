# Functional Requirements
1. user can search for events.
2. user view an event.
2. user can book a ticket for an event.

# Non Functional Requirements
1. Consistency: No two user will book the same ticket.
2. search event have low latency.
3. High availability: user can view and search event.
4. Handle popular event booking.

* Event read >> write

# Core Entities
Event
Ticket
Venue

# API or System Interface

## View Event
```HTTP
GET events/{event-id} -> event & venue & performer & ticket[]
```
## Search Event
```HTTP
GET events/search?term={term}&location={location}&type={type}&date={date} -> partial data of event
```
## Book Ticket
```HTTP
POST ticket/reserve
Header: JWT token | session token
body: {
    ticketId
}
```
```HTTP
POST ticket/confirm
Header: JWT token | session token
body: {
    ticketId,
    payment_detail
}
```
# High Level Design

# Deep Dive
