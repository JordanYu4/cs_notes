## KSUID

- K-Sortable Unique Identifier 
- Similar to RFC 4122 UUIDs, but contain component that allows rough time-sorting by creation 
  - "Depends on wall clocks" 
- Useful for distributed systems 
  - Other common choice: UUIDv4

### Features: 
1. #### Sortable by timestamp
2. #### Doesn't require coordination, reducing complexity of implementation and operations overhead (unlike snowflake IDs and derivatives)
    - RFC 4122 UUIDv1 has a time component, but not enough bytes of randomness to reliably protect against duplicate generation 
3. #### Lexographically sortable, protable representaiotns  
    - Integrate easily into systems that don't natively support KSUIDs, while still remaining k-sortable 
    - String representation is base62-encoded (acceptable wherever alphanumeric strings accepted)

#### Sources 
- [Segment IO KSUID golang package](https://github.com/segmentio/ksuid)