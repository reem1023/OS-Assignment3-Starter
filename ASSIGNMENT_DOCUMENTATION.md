# Assignment 3 - Complete Documentation

Student Name: ريم العنزي
Student ID: 443051761
Date Submitted: 27 April 2026

---

## 🎥 VIDEO DEMONSTRATION LINK (REQUIRED)

> **⚠️ IMPORTANT: This section is REQUIRED for grading!**
> 
> Upload your 3-5 minute video to your **PERSONAL Gmail Google Drive** (NOT university email).
> Set sharing to "Anyone with the link can view".
> Test the link in incognito/private mode before submitting.

**Video Link**: [Paste your personal Gmail Google Drive link here]

**Video filename**: `[YourStudentID]_Assignment3_Synchronization.mp4`

**Verification**:
- [ ] Link is accessible (tested in incognito mode)
- [ ] Video is 3-5 minutes long
- [ ] Video shows code walkthrough and commits
- [ ] Video has clear audio
- [ ] Uploaded to PERSONAL Gmail (not @std.psau.edu.sa)

---

## Part 1: Development Log (1 mark)

Document your development process with **minimum 3 entries** showing progression:

### Entry 1 - [Date, Time]
**What I implemented**: Added ReentrantLock and Semaphore imports

**Challenges encountered**: 

**How I solved it**: Reviewed TODO comments

**Testing approach**: 

**Time spent**: 

---

### Entry 2 - [Date, Time]
**What I implemented**: Added locks for shared counters.

**Challenges encountered**: 

**How I solved it**: Used one shared lock.

**Testing approach**: 

**Time spent**: 

---

### Entry 3 - [Date, Time]
**What I implemented**: Added lock for execution log.

**Challenges encountered**: 

**How I solved it**: Used separate log lock.

**Testing approach**: Checked add method.

**Time spent**: 

---

### Entry 4 - [Date, Time]
**What I implemented**: Added CPU semaphore.

**Challenges encountered**: 

**How I solved it**: Added try/finally.

**Testing approach**: Code tracing.

**Time spent**: 

---

### Entry 5 - [Date, Time]
**What I implemented**: Final review.

**Challenges encountered**: 

**How I solved it**: Fixed formatting.

**Testing approach**: 

**Time spent**: 

---

## Part 2: Technical Questions (1 mark)

### Question 1: Race Conditions
**Q**: Identify and explain TWO race conditions in the original code. For each:
- What shared resource is affected?
- Why is concurrent access a problem?
- What incorrect behavior could occur?

**Your Answer**:

[Two race conditions were counter variables and executionLog. Multiple threads may update counters at the same time causing lost updates. Also multiple threads may write to ArrayList simultaneously causing corruption or exceptions. Locks solve this issue.]

---

### Question 2: Locks vs Semaphores
**Q**: Explain the difference between ReentrantLock and Semaphore. Where did you use each in your code and why?

**Your Answer**:

[ReentrantLock gives mutual exclusion to one thread at a time. Semaphore controls access count to resources. I used locks for counters and logs, and semaphore for CPU access because only one process should run at once.]

---

### Question 3: Deadlock Prevention
**Q**: What is deadlock? Explain TWO prevention techniques and what you did to prevent deadlocks in your code.

**Your Answer**:

[Deadlock is when threads wait forever for resources. Prevention methods are releasing locks in finally block and keeping lock usage simple. I used try-finally so locks always release.]

---

### Question 4: Lock Granularity Design Decision 
**Q**: For Task 1 (protecting the three counters), explain your lock design choice:
- Did you use ONE lock for all three counters (coarse-grained) OR separate locks for each counter (fine-grained)?
- Explain WHY you made this choice
- What are the trade-offs between the two approaches?
- Given that the three counters are independent, which approach provides better concurrency and why?

**Your Answer**:

[I used one lock for all counters. It is easier and safer to manage. Separate locks may improve concurrency but increase complexity. Since counters are simple shared values, one lock was enough.]

---

## Part 3: Synchronization Analysis (1 mark)

### Critical Section #1: Counter Variables

**Which variables**:  contextSwitchCount, completedProcessCount, totalWaitingTime  

Why they need protection: Multiple threads may update values simultaneously causing wrong totals.

Synchronization mechanism used: ReentrantLock

Justification: Ensures one thread updates counters at a time.

Critical Section #2

What resource: executionLog

Why it needs protection: Multiple threads writing together may corrupt ArrayList.

Synchronization mechanism used: ReentrantLock

Justification: Prevents concurrent modifications.

Critical Section #3

Purpose of semaphore: Control CPU access.

Number of permits and why: 1 permit because only one process should run.

Where implemented: Inside run() method.

Effect on program behavior: Simulates one CPU process at a time.
---

## Part 4: Testing and Verification (2 marks)
Test 1 Results:

Program produced stable outputs across runs.

Why synchronization is necessary:

Without locks, counters may be incorrect and logs may fail.

Conclusion:

Synchronization improved correctness.

Test 2 Testing procedure:

Ran program multiple times.

Results:

No ConcurrentModificationException.

What this proves:

Log protection works.

Test 3 Expected values:

Completed processes should equal created processes.

Actual values:

Values matched.

Analysis:

Program worked correctly.

Test 4 Scenario tested:

Different random generated processes.

Purpose:

Check stability.

Results:

Program completed normally.

What I learned:

Synchronization works in different scenarios.
---

## Part 5: Reflection and Learning

### What I learned about synchronization:

[I learned synchronization protects shared resources. Locks prevent race conditions. Semaphores limit access to resources. try-finally helps release locks safely. Thread safety is important in Java. Shared data must be controlled carefully.

**Example 1**: Banking systems  

**Example 2**: Printer queues]



---

### How I would explain synchronization to others:

[Synchronization is like giving one key to one room. Only one person can enter at a time to avoid problems.]

---

## Part 6: GitHub Repository Information

**Repository URL**: 

**Number of commits**: 4

**Commit messages**: 
1. Set student ID

2. Add locks

3. Add semaphore

4. Complete documentation 

---

## Summary

**Total time spent on assignment**: 

**Key takeaways**: 
1. 
2. 
3. 

**Most challenging aspect**: 

**What I'm most proud of**: 

---

**End of Documentation**
