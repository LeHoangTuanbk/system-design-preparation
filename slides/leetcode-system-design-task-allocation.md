#Presentation task's allocation:

## Tuan starts from here:

1. Requirements

- Functional
- View problem
- Submission
- Contest
  Non-functional:
- Latency: từ luc submit den nhan ket qua < 5s.
- Latency contest leaderboard: 10s.
- Code execution: security

2. Back of the Envelope Estimation

- Contest: 10^5 users, submit: 10 times => 10^6 submit / 120 = 10,000 / minutes = 160 submissions/s

3. API design

- getProblem
- getProblems
- submit(problemId)

4. Data model design
   Table:

- Users
- Problems
- Submission
- Contest

## Long starts here:

5. High level design

- During the contest
- Components:Client, Server, DB, Queue, Code execution, Redis: worker

6. Discussion

- Length of queue
- Pike submission
- How will the system support isolation and security when running user code
