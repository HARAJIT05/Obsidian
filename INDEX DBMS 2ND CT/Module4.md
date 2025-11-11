## Module 4: Transactions and Concurrency

### 1. [[Transactions]]
A transaction is a single logical unit of work that accesses and possibly modifies the contents of a database. Transactions are treated in a coherent and reliable way, independent of other transactions.

### 2. [[ACID Properties]]
The four ACID properties of a transaction are:
- **[[Atomicity]]**: Ensures that a transaction is treated as a single, indivisible unit. Either all of its operations are executed, or none are.
- **[[Consistency]]**: Guarantees that a transaction brings the database from one valid state to another.
- **[[Isolation]]**: Ensures that concurrent transactions do not interfere with each other. It provides the illusion that transactions are executed serially.
- **[[Durability]]**: Ensures that once a transaction has been committed, its changes are permanent, even in the event of a system failure.

### 3. [[Concurrent Transactions]]
Database systems allow concurrent transactions to improve overall throughput and resource utilization. By allowing multiple transactions to run simultaneously, the system can process more work in less time, leading to better performance.

### 4. [[Concurrency Problems]]
- **[[Lost Update Problem]]**: Occurs when two transactions access and modify the same data item, and the changes of one transaction are overwritten by the other.
- **[[Dirty Read Problem]]**: Happens when a transaction reads data that has been modified by another transaction that has not yet committed. If the modifying transaction rolls back, the first transaction has read "dirty" data.
- **[[Non-repeatable Read Problem]]**: Occurs when a transaction reads the same data item twice and gets different values because another transaction has modified the data in between the reads.
- **[[Phantom Read Problem]]**: Occurs when a transaction re-executes a query returning a set of rows that satisfies a search condition and finds that additional rows have been inserted by another committed transaction.

### 5. [[Locking Protocols]]
A locking protocol is a set of rules that governs how transactions acquire and release locks on data items. The purpose is to control concurrent access to data and prevent interference between transactions, thereby ensuring data consistency.

### 6. [[Lock Types]]
- **[[Shared Lock (S-lock)]]**: A shared lock (S-lock) allows a transaction to read a data item. Multiple transactions can hold a shared lock on the same item simultaneously, allowing for concurrent reads.
- **[[Exclusive Lock (X-lock)]]**: An exclusive lock (X-lock) allows a transaction to both read and write a data item. When a transaction holds an exclusive lock, no other transaction can acquire any lock (shared or exclusive) on that item.
- **[[Multiple Granularity Locking]]**: A locking strategy that allows locks to be placed on different levels of the database hierarchy (e.g., table, page, row). This provides a flexible approach to locking, balancing concurrency and overhead.
- **[[Intention Lock]]**: An intention lock (e.g., IS, IX) is a type of lock used in multiple granularity locking. It signals the intention of a transaction to acquire a lock on a finer-grained object, preventing conflicting locks on coarser-grained objects.

### 7. [[Serializable Schedules]]
A serializable schedule is a schedule of concurrent transactions that is equivalent to some serial schedule (a schedule where transactions are executed one after another). It is important because it guarantees that the execution of concurrent transactions will leave the database in a consistent state.

### 8. [[Types of Serializable Schedules]]
- **[[Conflict Serializable Schedule]]**: A schedule is conflict serializable if it can be transformed into a serial schedule by a series of non-conflicting swaps of adjacent operations.
- **[[View Serializable Schedule]]**: A schedule is view serializable if it is view equivalent to some serial schedule. This is a more general form of serializability than conflict serializability.

### 9. [[Two-Phase Locking (2PL)]]
Two-Phase Locking (2PL) is a concurrency control protocol that ensures serializability. It consists of two phases: a growing phase, where a transaction can acquire locks but cannot release any, and a shrinking phase, where it can release locks but cannot acquire any new ones.

### 10. [[Strict Two-Phase Locking]]
Strict Two-Phase Locking is a variant of 2PL where a transaction holds all its exclusive locks until it commits or aborts. This prevents other transactions from reading uncommitted data and simplifies recovery. A major benefit is that it avoids cascading rollbacks.

### 11. [[Deadlock]]
A deadlock is a situation where two or more transactions are waiting for each other to release locks, resulting in a standstill where no transaction can proceed. This can happen in any system with concurrent processes and shared resources.

### 12. [[Deadlock Handling]]
- **[[Wait-Die Scheme]]**: A deadlock prevention scheme where if a transaction T1 requests a lock held by T2, T1 is allowed to wait only if it is older than T2. Otherwise, T1 is rolled back (dies).
- **[[Wound-Wait Scheme]]"**: Another deadlock prevention scheme. If a transaction T1 requests a lock held by T2, T1 is allowed to wait if it is younger than T2. If T1 is older, it "wounds" T2 by forcing it to roll back.
- **[[Wait-For Graph (WFG)]]**: A deadlock detection method where a directed graph is created with nodes representing transactions. An edge from T1 to T2 means T1 is waiting for T2. A cycle in the graph indicates a deadlock.
- **[[Timeout Approach]]**: A simple deadlock handling approach where a transaction is aborted if it has been waiting for a lock for more than a predefined amount of time. This is easy to implement but may abort transactions that are not actually deadlocked.

### 13. [[Concurrency Control Types]]
- **[[Pessimistic Concurrency Control]]**: Assumes that conflicts between transactions are likely to occur. It uses locking to prevent transactions from accessing data in a way that could cause conflicts.
- **[[Optimistic Concurrency Control (OCC)]]**: Assumes that conflicts between transactions are rare. It allows transactions to proceed without locking and checks for conflicts only at commit time. The three phases are read, validation, and write.
