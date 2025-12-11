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
- User analytics

---

# 2. Back of the Envelope Estimation

---
