# 1. First steps

Erlang was created to support **highly available** systems:

- Fault-tolerance
- Scalability
- Distribution
- Responsiveness
- Live update

Concurrency is the heart and soul of Erlang systems:

- Concurrency primitive is _Erlang process_
- Erlang VM is BEAM (Bogdan/Bjorn's Erlang Abstract Machine)
- BEAM uses its own schedulers to distrubte execution of processes over available CPU cores, while parallelizing execution

Benefits:

- Fault-tolerance: Erlang processes are isolated from each other: share no memory, and crash of one doesn't cause crash of other processes
- Scalability: share no memory, processes communicate via asynchronous messages; no complex synchronization mechanisms; take advantage of all available CPU cores
- Distribution: communication between processes are similiar in same BEAM instance or two different instances on two separate remote computers; if one machine crashes, others can take over
- Responsiveness: scheduler gives small execution window to each process and then pauses it and runs another process, a single long-running process can't block the rest of the system; per-process garbage collection: instead of stopping entire system, each process is individually collected as needed
