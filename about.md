**ZOOKEEPER** : It is a **Distributed Configuration Management System**

In distributed applications, we face major challenges such as, data inconsistency, and not having consensus(general agreement). And distributed systems, have to deal with maintaining consistency, a lot of efforts need to be put in, to overcome challenges in distributed Computing.

ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services.

Eg. Let's say, we want to know the ip addresses of all the machines in a distributed application, then ZK is the solution.
If we want to know, Which machine is master/slave.
Distributed Locking.
Service Discovering.

It is some kind of ORCHESTRATOR. 

Example Problem:
lets say, we have multiple App Servers [A1 to A7]
          3 masters[M1,M2,M3] having 2 slaves each[M1-1,M1-2],[M2-1,M2-2],[M3-1,M3-2]

          Now, Server A1 wants to write something to M3, it needs to reach M3. Similarly, if it want to read something, it needs to reach slaves of M3 i.e [M3-1,M3-2]

          In some other instance of time, we require to increase the number of shards in above application, then its info, needs to be stored somewhere.

          At other instance, let's say some machine dies, let's say a master dies, for some time writes to that machine will start failing. In this case, all the machine needs to know which machine is removed and which is the new elected master.

This is one of the example.

Let's try to build such a system intuitively.
Starting with a naive solution.

Let's say, I have an App Server A1 , and Master M1 with 3 slave machines S1,S2, S3.
            And a dedicated machine [DM], to keep all the information about the application. This machine keeps a constant watch on all the machines in the application.
            So, Whenever A1 needs to know the ip address of any M1 machine, it can simply reach to DM and ask the ip address. And then approach to M1.

**PROBLEMS** : 
1. Single Point Of Failure (SPOF) of dedicated machine.
2. Additional Hop in every request. [Increasing Latency]

