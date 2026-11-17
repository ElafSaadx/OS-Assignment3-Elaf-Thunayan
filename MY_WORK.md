# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Elaf Saad AlThunayan] |
| **Student ID** | [446051372] |
| **University Email** | [446051372]@std.psau.edu.sa |
| **GitHub Username** | [ElafSaadx] |
| **Repository Link** | [https://github.com/ElafSaadx/OS-Assignment3-Elaf-Thunayan] |
 
---

## 🎥 Video Link

**Video Link**: [https://youtu.be/Y1PJCrMeJIQ?si=4JosRIKtY0ogQDqO]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 17, 2026, 6:21 PM]
**What I did**:Set my student ID and prepared the project.

**Details**:
Updated the student ID in SchedulerSimulationSync.java to 446051372.

Checked that the program uses my student ID to generate the simulation parameters.

Saved the change in Git.

**Challenges**:I needed to make sure that the simulation used my own student ID so that the expected verification values would be correct.

**Solution**:I checked the student ID in the source code and confirmed that it was used as the random seed.

**Time spent**: 30 minutes

---

### Entry 2 - [November 17, 2026, 7:00 PM]
**What I did**:did Feature 1: Ready Queue Synchronization.

**Details**:
Added a ReentrantLock to protect the shared ready queue.

Protected add(), poll(), processOf(), and snapshot().

Used try/finally to make sure the lock is always released.

**Challenges**:Multiple CPU threads could access the linked list at the same time, which could cause two CPUs to select the same process.

**Solution**:I used a mutex lock to ensure mutual exclusion whenever a thread accesses the shared queue.

**Time spent**:1 hour

---

### Entry 3 - [November 17, 2026, 7:55 PM]
**What I did**:Implemented Feature 2: Shared Statistics Synchronization.

**Details**:
Added separate locks for contextSwitchCount, completedProcessCount, and totalServiceTime.

Protected all three update methods and their corresponding getter methods.

Used try/finally in every locked section.

**Challenges**:The statistics were shared between multiple threads, so simultaneous updates could cause lost updates and incorrect verification results.

**Solution**:I used one lock per independent statistic to prevent concurrent modifications while allowing unrelated statistics to be updated independently.

**Time spent**:1 hour

---

### Entry 4 - [November 17, 2026, 8:58 PM]
**What I did**:Implemented Feature 3: Counting Semaphore.

**Details**:
Added a counting semaphore to the ready queue.

Initialized the semaphore with zero permits.

Added release() when a process is added to the queue.

Replaced the CPU polling loop with acquire().

Added a shutdown signal to wake up CPUs when all processes are completed.
**Challenges**:
I needed to prevent CPUs from continuously checking an empty queue and make sure that blocked CPUs could terminate when the simulation finished.
**Solution**:
I used a counting semaphore to block CPUs until a process becomes available and added a shutdown signal to wake the remaining CPUs.
**Time spent**: 1 hour and 15 minutes

---

### Entry 5 - [November 17, 2026, 9:30 pm]
**What I did**:Re-Ran the original starter and checked the final implementation.

**Details**:
Ran the original starter with my student ID before applying synchronization fixes.

Observed two CPUs selecting P1 and an IllegalThreadStateException.

Observed the watchdog message and incorrect verification values.

Checked the final implementation and its verification output.

**Challenges**: The original program had multiple concurrency problems, and the output was difficult to understand at first.

**Solution**:I compared the starter output with the final verification results and reviewed the synchronization mechanisms used in the code.

**Time spent**:30 minutes

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [4-5 hours]

**Most challenging part**:Understanding how several CPU threads might simultaneously access the same ready queue was the most difficult aspect. I was initially confused as to how two CPUs might choose the same process. I realized that reading and deleting an item need to be protected as a single crucial section after looking at the poll() method.

**Most interesting learning**:The most interesting thing I learned was how a counting semaphore can replace busy waiting. Instead of repeatedly checking whether the queue is empty, a CPU can block until a process becomes available.

**What I would do differently next time**:
I would start testing the program earlier and implement one synchronization feature at a time.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** (I discovered that when several threads access shared data simultaneously, synchronization is required. When two threads execute a read-modify-write operation without adequate protection, a race condition may result. I utilized ReentrantLock in this assignment to safeguard shared statistics and important portions of the ready queue. I also discovered that, even in the event of an exception, all locks should be released within a finally block. I was able to comprehend how threads can wait without constantly utilizing the CPU thanks to the counting semaphore. I was taken aback by the initial starter since two CPUs chose the same process, resulting in an IllegalThreadStateException.)

[Write your answer here.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The hardest part was finding and fixing the race condition in the ready queue. The problem was difficult because there were several CPU threads that were accessing the same linked list at the same time. Two CPUs might read the same first process before they take it out of the queue. This caused the same process to be selected more than once and could cause exceptions or processes to be lost. But I also had to make sure all queue operations were guarded including snapshot() and processOf(). I understood why the whole queue operation needed mutual exclusion and that helped me to solve this problem.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[By reading the assignment instructions and looking closely at the starter code, the challenges were overcome. First I ran the original program and noted down the exceptions and wrong check values. After that I divided the implementation into three features and worked on them in the required order. I used ReentrantLock for the shared queue and statistics and added a counting semaphore to replace busy waiting. I also reviewed the output after I added in the synchronization features to make sure the changes were working as expected. Reviewing the mistakes and asking for help allowed me to grasp the parts that were confusing at first..]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization is crucial in many real world applications where many users or processes access shared resources. For example, in a banking system synchronization is used to prevent two transactions from incorrectly updating the same account balance. Ticket booking systems need to be synchronized so that two customers do not book the same seat. Synchronization can be used to organize print jobs in a printer queue . To avoid conflicts between users . Locks are also used in databases to protect shared records in transactions. These examples are similar to my assignment in that multiple threads are accessing shared data and need controlled access to prevent inconsistent results.
]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[The original starter code had race conditions because multiple CPU threads accessed the shared ready queue without synchronization. In my output, CPU-1 and CPU-2 both selected P1, which caused an IllegalThreadStateException when the same process was started again. The verification also showed incorrect results: 35 context switches were expected but only 32 were observed, and 14 completed processes were expected but only 13 were observed. These problems demonstrate that concurrent operations on shared data can produce lost updates and inconsistent results.]

Verification block of the **original starter**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected ٣٥       observed ٣٢       ✘ MISMATCH
  Completed processes                    expected ١٤       observed ١٣       ✘ MISMATCH
  Total service time (ms)                expected ١٣٥٧٤٣   observed ١٢٣٩٥١   ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected ٠        observed ١٤٩٤     ✘ MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
]
```

Verification block of **my final version**:
```
[═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected ٣٥       observed ٣٥       ✔
  Completed processes                    expected ١٤       observed ١٤       ✔
  Total service time (ms)                expected ١٣٥٧٤٣   observed ١٣٥٧٤٣   ✔
  Busy-waiting polls (must be 0)         expected ٠        observed ٠        ✔
  ✔ All shared values are consistent.
]
```

**Explanation of the timeline:**
[For example, suppose completedProcessCount is 12. CPU-1 reads the value 12, and before it writes the updated value, CPU-2 also reads 12. CPU-1 writes 13, and then CPU-2 writes 13 as well. The correct value should be 14, but one increment is lost because both CPUs used the same old value. This can happen on a real machine without RaceWindow.pause() because the operating system can interrupt and switch between threads at unpredictable times.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used a ReentrantLock for the ready queue, and one for each of the three independent statistics. The locks protect both the update methods and the getter methods. They enforce mutual exclusion every time a shared data structure is accessed. Separate statistics locks allow the independent counters to be updated independently of each other without unnecessarily blocking each other, but require you to manage more locks. The ready queue has its own lock as the operations on it protect a different shared resource and should not be blocked by unrelated statistics operations. The locks provide mutual exclusion and allow progress on lock release by a thread, but the default non-fair ReentrantLock does not guaranty bounded waiting, so starvation is theoretica]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [queueLock] | [Protects adding processes to the shared list and map.] |
| [ReadyQueue.poll()] | [queueLock] | [Prevents two CPUs from removing or selecting the same process.] |
| [ReadyQueue.snapshot()] | [queueLock] | [Prevents concurrent modification while iterating over the queue.] |
| [incrementContextSwitch() and its getter] | [contextSwitchLock] | [Prevents lost updates and inconsistent reads.] |
| [incrementCompletedProcess() and its getter] | [completedProcessLoc] | [Protects the completed-process counter.] |
| [addServiceTime() and its getter] | [serviceTimeLock] | [Prevents lost updates to the total service time.] |


## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[n the original starter, a CPU implemented busy waiting by constantly checking the ready queue and sleeping for 20 milliseconds if the ready queue was empty. My starter output showed 1491 busy-waiting polls, which means that CPUs were polling the queue instead of blocking. In my last implementation the counting semaphore's initial value is zero because there are no processes available before the initial add() calls. When the 14 initial processes are added, the value of the semaphore becomes 14, which means that there are 14 processes available. When the last process is finished , the CPU releases permits to the other CPUs so that any blocked threads can wake up and terminate . Without this shutdown signal they could remain blocked forever .

Question 4 Classical Problem]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This assignment is, about the producer-consumer problem. In this problem the code that puts processes into the queue is the producer and the CPUs are the consumers. The CPUs can also act as producers when the CPUs requeue unfinished processes. If the queue has a fixed capacity of K then three semaphores are used. The empty semaphore starts at K the full semaphore starts at 0. The mutex semaphore starts at 1. A deadlock can happen if a producer takes the mutex and then waits for a slot while a consumer also needs that mutex to take an item and create a free slot. To avoid this deadlock the producer should first wait for a slot before taking the mutex.
**Classical problem and roles**:
[Problem: Producer-Consumer problem.
Producer: The code that adds processes to the ready queue, including CPUs re-enqueuing unfinished processes.
Consumer: The CPU workers that remove processes from the ready queue.]

**Semaphores for a bounded queue (name and initial value)**:
[empty = K: Number of available empty slots.
full = 0: Number of available items.
mutex = 1: Ensures mutual exclusion when accessing the queue.]

**Deadlock scenario and prevention**:
[A producer may acquire the mutex and then wait because the queue is full. If a consumer needs that same mutex to remove an item, it cannot proceed, so the producer and consumer remain blocked. This creates a deadlock caused by hold-and-wait. The condition can be prevented by waiting for the required semaphore before acquiring the mutex, so a thread does not hold the mutex while waiting for a resource.]

## Summary

**Key concepts I understood through these questions:**
1.Race conditions occur when multiple threads access shared data without proper synchronization.
2.ReentrantLock provides mutual exclusion for critical sections.
3.Counting semaphores allow threads to block until resources become available instead of using busy waiting.

**Concepts I need to study more:**
1.Deadlock prevention and the four necessary conditions for deadlock.
2.Fairness, starvation, and bounded waiting in concurrent systems.
---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
