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
GET events/{event-id} -> event & venue & performer & ticket[]

## Search Event
GET events/search?term={term}&location={location}&type={type}&date={date} -> partial data of event

## Book Ticket
POST ticket/reserve
header JWT token | session token
```JSON
body: {
    ticketId
}
```

POST ticket/confirm
header JWT token | session token
```JSON
body: {
    ticketId,
    payment_detail
}
```
# High Level Design

# Deep Dive
