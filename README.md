**What is Uber?**
Uber is a mobility service provider, allowing users to book rides and a driver to transport them in a way similar to a taxi. It is available on the web and mobile platforms such as Android and iOS.

To study any case study, we follow these 4 steps:
  1. Minimum Viable Product(MVP)
  2. Estimation Of Scale
  3. Design
  4. Design Deep Dive

1. **Minimum Viable Product(MVP):**
   **Customers:**
     a. Customers should be able to see cabs in the vicinity with an ETA and Pricing Information.
     b. Customer should be able to book a cab to a destination.
     c. Customer should be able to see the location of the driver.

   **Drivers:**
     a. Drivers should be able to accept/deny customer's requested ride.
     b. Once the driver accepts the ride, they should see the pickup location of the customer.
     c. Driver should be able to mark the trip as complete, on reaching the destination.

   **Non-Functional Requirements:**

     a. High reliability
     b. High availability with minimal latency
     c. System should be scalable and efficient.

   **Extended Requirements:**

   a. Customers can rate the trip after it’s completed.
   b. Payment processing.
   c. Metrics and analytics.

**2. Estimation Of Scale**
Let us assume, we have 
**100 million daily active users (DAU)** with
**1 million driver**s and on average our platform enables 
**10 million rides daily**.

If on average each user performs 10 actions (such as request a check available rides, fares, book rides, etc.) we will have to handle **1 billion requests daily**.
60487 100 \space million \times 10 \space actions = 1 \space billion/day 60487

**What would be Requests Per Second (RPS) for our system?**

1 billion requests per day translate into 12K requests per second.

60487 \frac{1 \space billion}{(24 \space hrs \times 3600 \space seconds)} = \sim 12K \space requests/second 60487

**Storage**
If we assume each message on average is 400 bytes, we will require about 400 GB of database storage every day.

60487 1 \space billion \times 400 \space bytes = \sim 400 \space GB/day 60487

And for 10 years, we will require about 1.4 PB of storage.

60487 400 \space GB \times 10 \space years \times 365 \space days = \sim 1.4 \space PB 60487

**Bandwidth**
As our system is handling 400 GB of ingress every day, we will a require minimum bandwidth of around 4 MB per second.

60487 \frac{400 \space GB}{(24 \space hrs \times 3600 \space seconds)} = \sim 5 \space MB/second 60487

**High-level estimate**
Here is our high-level estimate:

| Type | Estimate | | — — — — — — — — — — — — — | — — — — — — | | Daily active users (DAU) | 100 million | | Requests per second (RPS) | 12K/s | | Storage (per day) | ~400 GB | | Storage (10 years) | ~1.4 PB | | Bandwidth | ~5 MB/s |
