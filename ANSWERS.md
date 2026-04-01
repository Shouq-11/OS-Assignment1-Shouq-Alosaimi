# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

A thread\ is a smaller unit of execution inside a process that shares memory, whereas a process is an independent application running with its own memory and system resources. Threads are faster and lighter than processes, which are heavier and require more time to construct and switch between.Another significant distinction is that threads share memory, enabling quicker communication, but processes do not.
In order to simulate CPU scheduling using the Round-Robin technique, threads were used in this assignment since they allow for efficient concurrent execution and speedier context switching.

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Round-Robin scheduling removes a process from the CPU and places it at the end of the ready queue if it doesn't complete within its time quantum. This guarantees equitable CPU sharing among all processes and permits other processes to run. Only when it gets to the front of the queue after every other process has had a chance will the process restart.

Example from my output:
   P7 executing quantum [4000ms]
   Remaining time: 2521ms
   P7 yields CPU for context switch
   P7 added to ready queue
```
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]

This example demonstrates that process P7 began running and utilized its entire 4000 ms time quantum, although it still had 2521 ms left. It ceded the CPU because it didn't finish, indicating that a context switch took place. The procedure was then moved back to the end of the ready queue. Before starting up again and carrying on with its execution, it will wait until every other process in the queue has had a chance.


---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

Throughout its existence, a thread travels through a number of states, which we can see in the simulation for process P1. P1, which stands for the New state, is first created but has not yet begun. It then enters the Runnable state and waits for CPU allocation after being added to the ready queue. It enters the Running state when the scheduler chooses P1 and it begins to execute its burst time (3224 ms). In this particular output, P1 does not enter a lengthy waiting state since it completes within its time quantum, however typically a process would enter waiting for the CPU once more or to see if it has been paused. Ultimately, P1 enters the Terminated state after finishing execution with 0 ms remaining.


1. **New**: [When is P1 in New state?]: Prior to being placed to the ready queue, P1 is initially in the New state.

2. **Runnable**: [When does P1 become Runnable?]: When P1 is added to the ready queue, it becomes Runnable (P1 added to ready queue).

3. **Running**: [When is P1 Running?]: When P1 begins to execute, it is running (P1 executing quantum [3224ms]).

4. **Waiting**: [When/why would P1 be Waiting?]: P1's entry is unclear This output is waiting since it completes in a single quantum, but if it were re-queued, it would typically wait.

5. **Terminated**: [When is P1 Terminated?]: P1 is terminated at completion of execution (P1 completed execution!).

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]


 Background Tasks for Mobile Apps


**Description**: 
[Describe the real-world scenario or application]

Several background processes, including data syncing, notification checking, and app updates, operate concurrently on a smartphone. Every task can be thought of as a thread that needs CPU time to complete. These duties must be handled by the system without compromising the user experience.

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

Every background job receives an equal amount of CPU time thanks to round-robin scheduling. This keeps the gadget from becoming slow due to a single task using all of its resources. Because tasks are completed in brief bursts of time, it also enhances responsiveness. Consequently, the phone continues to function well while managing several tasks.

### Example 2: [Name of application/scenario]

Platform for Streaming Videos

**Description**: 
[Describe the real-world scenario or application]

Many viewers can watch videos simultaneously on a video streaming platform. To load, buffer, and play video data, each user stream can be thought of as a thread that requires CPU time. All users must receive uninterrupted, seamless service from the system.

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

Every user stream receives an equal amount of CPU time thanks to round-robin scheduling. This keeps a single user from soaking up all available resources and creating buffering for other users. By regularly updating each stream in brief time slices, it increases responsiveness. Smoother playback and an improved user experience result from this. 

---

## Summary

**Key concepts I understood through these questions:**
1. I knew how to monitor a process's running, waiting, and termination states as it was being executed.
2. I realized that rather than being distinct processes, processes are carried out as threads inside the same software. 
3.I discovered how Round-Robin scheduling distributes CPU time among processes in an equitable manner.   
   

**Concepts I need to study more:**
1. I'd like to know more about decreasing context switches and enhancing scheduling performance.
2. I need to learn more about managing resources across several threads at once.
