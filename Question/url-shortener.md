# Functional Requirements
1. user create a shorten URL from original long URL
2. user use shorten URL, will be redirect to long URL
3. optional: expiration time
4. optional: alias

# Non Functional Requirements
1. consistent shortenURL <-> longURL mapping
2. Low redirection latence < 200 ms
3. High availability, eventual consistency for url shortening
4. Scale: support 100M DAU and 1B Urls

## CAP Theorem


# Core Entities
- longUrl
- shortUrl
- user
- expirationTime?
- alias?

# API or System Interface

POST /urls -> shortUrl
```JSON
{
    longUrl,
    alias?,
    expirationTime?,
}
```

GET /{shortUrl} -> Redirect to longUrl

302: 
- Pros: usage tracking
- Cons: heavy service usage

301:
- Pros: no more service usage after cached.
- Cons: not hitting service anymore

# Data Flow

# High Level Design
<img width="1288" alt="Image" src="https://github.com/user-attachments/assets/8be89c30-3a0b-40b0-a482-b128cc1c1295" />

# Deep Dive
