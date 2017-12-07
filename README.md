# Project 5: Distributed, Replicated Key-Value Store

### High level approach
We implemented the protocol in stages, as follows:
* Determined how to do leader elections, all data is store exclusively in leader
* Tried to implemented the distributed logs with commit consensus, but hit election issues
* Fixed elections so that replicas can only vote once and statuses are correctly assigned post-election
* Fixed elections that only replicas with the most committed log entries can be elected
* Resolved issues with the partition tests

### Challenges faced
* The dynamically typed nature of Python led to a few minor bugs
* Understanding that the "Leaders" part of output from the run script doesn't strictly give all leaders as our implementation knows them, but rather as it sees in information from the messages being sent
* Debugging can be a bit difficult with so many messages
* Trying to figure out exactly what constants we should be using for optimal performance, and why the values we chose are significant

### Testing methodology
* Use the run script with the given configs
* Run test script both on local machines and on CCIS servers