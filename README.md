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