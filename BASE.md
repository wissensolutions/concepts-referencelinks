
The BASE acronym was defined by Eric Brewer, who is also known for formulating the CAP theorem.

The CAP theorem states that a distributed computer system cannot guarantee all of the following three properties at the same time:

1. Consistency
2. Availability
3. Partition tolerance

A BASE system gives up on consistency.

1. **Basically available** indicates that the system does guarantee availability, in terms of the CAP theorem.
2. **Soft state** indicates that the state of the system may change over time, even without input. This is because of the eventual consistency model.
3. **Eventual consistency** indicates that the system will become consistent over time, given that the system doesn't receive input during that time.
