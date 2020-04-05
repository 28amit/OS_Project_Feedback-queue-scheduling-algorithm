Multi-Level Feedback Queue Scheduling Algorithm

Multilevel Feedback Queue Scheduling – 

•	In a multilevel queue-scheduling algorithm, processes are permanently assigned to a queue on entry to the system. Processes do not move between queues. This setup has the advantage of low scheduling overhead, but the disadvantage of being inflexible.

•	Multilevel feedback queue scheduling, however, allows a process to move between queues.

•	The idea is to separate processes with different CPU-burst characteristics. If a process uses too much CPU time, it will be moved to a lower-priority queue.

•	Similarly, a process that waits too long in a lower-priority queue may be moved to a higher priority queue. This form of aging prevents starvation.

•	Multilevel Feedback Queue Scheduling (MLFQ) keep analyzing the behavior (time of execution) of processes and according to which it changes its priority.



In general, a multilevel feedback queue scheduler is defined by the following parameters:

•	The number of queues.

•	The scheduling algorithm for each queue.

•	The method used to determine when to upgrade a process to a higher-priority queue.

•	The method used to determine when to demote a process to a lower-priority queue.

•	The method used to determine which queue a process will enter when that process needs service.



C program to simulate multilevel feedback queue scheduler


Multi-level feedback queue scheduler Q consists of 3 linear queues, i.e., Q1, Q2, and Q3.

Q1 is round robin with time quantum 8 (RR8)

Q2 is round robin with time quantum 16 (RR16), and

Q3 follows first come first serve (FCFS)



The process cannot be executed in the lower queue if there are any jobs in all higher queues. For example, Q1 has 5 processes, Q2 has 1 process, and Q3 has 1 process. Then, first the process in Q1 should be executed (and completed), and then a process in Q2 is executed. Finally, Q3 will get CPU resource.
A new process enters queue Q1 which is served RR5. • When it gains CPU, a process receives 5 milliseconds. • If it does not finish in 5 milliseconds, the process is moved to queue Q2. • At Q2 process is again served RR8 and receives 8 additional milliseconds. • If it still does not complete, it is preempted and moved to queue Q3. • At Q3 process is executed by first come first serve. • If it still does not complete, it is processed at Q2 until completed.
OUTPUT: The remaining time of processes in each queue level, total waiting time and total turnaround time are displayed. 
