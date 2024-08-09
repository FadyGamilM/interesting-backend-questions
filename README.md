# interesting-backend-questions
Just taking notes about questions I'd love to be asked in my next interview 

# What should u do if you have a resource in your database, and 2 requests came at the same time, one needs to update field-x and the other to update field-y ?
![optimistic lock](optimistic-lock.png)

# What do you know about indexes in database ?
- Hash Map Index 
    - stored in memory (RAM) so its not durable 
    - very fast O(1) for reads and write 
    - invalid for range queries [slow]

- BTrees index 
    - stored in disk (durable)
    - fast for reads, slow for writes 
    - valid for range queries [fast]

# could you explain the ACID transaction ?
- `Atomicity` :
    - All writes (insert - update - delete) fail togeather or succeed togeather.

- `Consistency` : 
    - we cannot have a corrupted data, and this is achieved by enforcing atomicity 
    - EXAMPLE : 
        * we must have one devops engineer at office at a time 
        * Dev-X takes a break 
        * Delete Dev-X from on-duty field 
        * Server crashes before Inserting Dev-Y 
        * NOW WE HAVE INCONSISTENT DATA 

- `Isolation` : 
    - a DB that satisfy the ACID couldn't have a race-condition 
    ![alt text](non-isolated-tx.png)

- `Durability` : 
    - once i committed a write, i shouldn't lose it if server goes down.

    ### Okay how to achieve the ACID ?
        ACD : can be achieved by using a WAL 