Outbox
======

A stream of notes from things I have watched/read.


## https://www.infoq.com/presentations/facebook-stream-processing

- Puma for stream
- Looking to build a unified


## https://www.infoq.com/presentations/serverless-security-2017

- Shows a few places where using unsafe JS libraries lets you access parts of a lambda container


## https://www.infoq.com/presentations/microservices-managing-data

- Good talk about why and how do deal with data with microservices
- Converting from monolith to microservices
- Don't start with microservices, there is a cost
- How do we do the following with microservices?
  - Shared Data
    - Events
    - Only _one_ canonical service still
  - Joins
    - Materialize views, listen to events in different service and aggregate what you need
  - Transactions
    - Sagas (workflows)


## https://www.infoq.com/presentations/agile-manifesto-principles-leader

- "Preserve dignity at all costs" @ 18:00


## https://www.infoq.com/presentations/http-http2-spdy-quic

- Good intro to SPDY -> HTTP/2 -> Quick
- Speed of light is a thing
- Roundtrips are the devil
- SPDY does multiplexing which is great for roundtrips
- _Everything_ has to be built on UDP and TCP, otherwise have to deal with hardware across the world
- Quic is built on UDP
- Quic is better than HTTP/2 because it doesn't have "Head of line blocking" which causes issues on unreliable networks (eg. mobile)
- Quic is being adopted by IETF which is great


## https://www.infoq.com/presentations/functional-performance

- Caching and hardware 101 (good intro)
- Universal scalability law (more accurate than Amdahl's law which didn't consider consensus)
- Pure FP DS are bad for hardware affinity - lots of pointer chasing (ie. link lists)
- Monotonic increasing integers are great for making things performance and reliable
- Borrows ideas from CRDTs
