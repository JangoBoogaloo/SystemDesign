# Requirements

## Functional Requirements
1. Set preference (age, gender, etc)
2. See candidates base on preference (close to location)
3. Like(right) or Not(left) candidate
4. Match if liked each other, receive notification
5. Create profile

### Constraints
1. Avoid showing repeat profile

## Non Functional Requirements
- Immediate match when 2 users like each other
- Get relevant profiles with low latench (<100ms)

### Consistency 
- for Swipes. Get most accurate write when read.
### Availability
- candidates loading (< 300ms)

### Scale
- 10M DAU
- each 100 swipe

10M * 100 swipes / day

# Core Entities
- User proifle
- Swipe
- Match

# API or System Interface

## Create profile
POST /users
```JSON
{
    minAge,
    maxAge,
    gender,
    radius,
}
```

## Get Candidates
GET /candidates?lat&long-> Profile[]
Header: JWT | session

## Swipe Candidate ->match?
POST /swipes/:userId
{
    decision: yes| no
}

# Data Flow

# High Level Design

# Deep Dive

## Immediate match when 2 users like each other

## Get relevant profiles with low latench
* What happens you change geo-location or other preference

## No repeat profiles
