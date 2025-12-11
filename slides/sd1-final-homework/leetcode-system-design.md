---
marp: true
theme: default
paginate: true
---

# Design Leetcode

Members: Tuan Le Hoang - Long Nguyen Hoang

---

# Agenda

1. Clarify Requirements
2. Back of the Envelope Estimation
3. API Design
4. Data Model Design
5. High-level Design
6. Detailed Design
7. Identify and Discuss Bottle necks

---

# 1. Clarify Requirements

---

# Functional Requirements

- View Problems
- Submit Solutions in multiple language
- Join Coding Contests
- Discussion

---

# Non-Functional Requirements

- Availability: 99.9% uptime
- Scalability: 10K+ current submissions
- Latency: Code execution < 10s, leaderboard update: < 5s
- Security: Isolated code execution, prevent malicious code

---

# Out of Scope

- User Authentication
- Payment processing
- User analytics / User management

---

# 2. Back of the Envelope Estimation

- Daily Active Users: 500,000
- Problems in DB: 4000
- Contest participants: 10,000
- Problems in DB: 3000+, growth: 8 problems/week => 418 problems/year

---

# Submission Estimation

- Leetcode has [26.3 milion](https://en.wikipedia.org/wiki/LeetCode) monthly visitors
  => 26.3 \* 10^6 / 30 / 86000 = 10 QPS
- Support 10+ popular programming Languages: Python 3, python 2, Java, C++, C, C#, C, Javascript, Typescript, Go, Swift, Rust, PHP, Kotlin...

```

Daily submissions:
    500,000 DAU * 3 = 1.5 M submissions/day
    => 1.5 * 10^6 / 86,000 = 17 submissions/second
    => 2 submissions/language/second


Peak submissions (contest):
    10,000 * 20 submissions = 200,000 in 90 minutes
    => 2 * 10^5 / 4800 = 41 submissions/second
    => 4 submissions/language/second
```

---

# Storage Estimation

```
Per submission:
    Code: ~10 KB
    Metadata: ~1KB
    Results: ~2 KB
    => Total: ~13 KB
    => Daily storage:
    1.5 M * 13 KB = 20 GB/day
    => Monthly storage growth: 600 GB/month

Problems + Test cases:
    3,000 * 50 test cases * 10 KB = 1.5 GB
```

---

# Bandwidth Estimation

```
Incoming (submissions):
    1.5 M * 10 KB = 15 GB/day

Outgoing
    Problem views: 10 M * 50 KB = 500 GB/day
    Results: 1.5 M * 5KB = 7.5 GB/day

=> Total: ~520 GB/day ≈ 6 MB/s average

```

---

# 3. API Design

---
