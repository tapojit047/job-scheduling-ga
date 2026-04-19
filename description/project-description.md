# Project 2

## Artificial Intelligence  
**Spring 2026**

**Distributed:** Monday 23 Feb 2026  
**Due Part A:** Monday 2 March 2026  
**Part B:** Monday 16 March 2026  

---

**[Solutions to this assignment must be submitted via CANVAS prior to midnight on the due date.]**

This project may be undertaken either individually or in pairs. Please state the names of the (person or persons undertaking the project and the contributions that each has made. Only ONE submission must be made per group.

---

## Purpose

To gain a thorough understanding of how the Genetic Algorithm (GA) can be applied to solve a real-world scheduling problem. Unlike the robot application in Project 1 this project will focus on a different type of scheduling problem, which is the **Job Shop scheduling problem**. This is a problem that occurs commonly in Industry across a number of different application domains. Some applications of job shop scheduling include process scheduling at a server farm, packet routing across a computer network, job scheduling at a manufacturing plant, amongst many others.

In job scheduling **J jobs** are scheduled for processing at **M machines**. Each job has a fixed number of operations (**N**). The problem then is to allocate the jobs and their corresponding operations such that the overall completion time (referred to as the **makespan**) is minimized.

Jot down any questions/doubts that you may have and feel free to ask me questions during office hours or in person. Working individually or with your partner, work out a strategy before you start coding the solution in Python. Given the limited timeframe for the project, some simplifications have been applied. In all cases, when simplifications are used, they have been pointed out explicitly. You may find it useful to compile  
a) a list of all functional requirements and  
b) a list of all assumptions before starting to code.

---

## Environment Description

The environment is a simple one consisting of jobs and machines. Jobs have different completion times but have no constraints as to their starting time. The only constraint on a job is that its operations must run in strict sequence. Thus, for example operation **J11 of job 1 must be scheduled before operation J12 of job 2**. All machines may be assumed to have the same processing power. The operational times for each job are known in advance.

---

## Job/Operation Scheduling

Scheduling is performed at the **Job level**, not at the operation level. Once an ordering of jobs is determined then that order is used consistently for all machines. Thus, if there are two machines, then the jobs execute in exactly the same sequence on both machines. The scheduler will exploit the availability of multiple machines by scheduling different job operations to run concurrently (at the same time) so as to minimize overall job completion time. Thus, an efficient schedule will maximize the use of **parallelism across machines** while minimizing **idle time** (i.e., waiting for other jobs to complete) on individual machines.

---

## Strategy

The overall strategy is to use the **GA algorithm** to perform scheduling. This will involve population generation, population selection, chromosome crossover and mutation. The details of these methods will be explained in the Notes for **Project 2 Discussion Document** accessible from `Project 2 Discussion Document.docx`.

---

# Project Requirements

## Part A

Produce the pseudo code needed for:

### R1
The **crossover operation**

### R2
To compute the **fitness value of a given chromosome**. The fitness computation should be generic enough to handle **any number of jobs (J)** and **any number of machines (M)**.

R1 and R2 are meant as thinking exercises prior to coding. All pseudo code must be typewritten and submitted in a **pdf document**. No handwritten versions will be accepted.

Part A needs to be submitted in a **typewritten original pdf (not an image of a pdf)** document. This is the only document that you need to submit for Part A.

---

## Part B

Fully implement the **Job Shop Scheduling Agent in Collab** for each of the 3 scenarios given as **R3, R4 and R5** below.

### R3
Use the jobs specified in **Table 1 of the Project 2 Discussion Document.docx**. Your code must be based on the design that you submitted for **R1 and R2** above and should display the **makespan** for this job mix.

Compare the makespan value that you obtain with the value **30** which is the **optimal makespan value**. For a definition of makespan see **Algorithm 1** in the Project 2 Discussion Document. The makespan represents the **fitness value of a chromosome once the chromosome is used for job scheduling**.

---

### R4
Create **10 jobs randomly with 3 operations per job**. For each job randomly generate the **3 operation times in the range [5,50]**. The jobs need to be scheduled for **5 machines**.

Questions:
- What is the **makespan value of the chromosome with the highest fitness value**?
- How does it compare with the value chosen from a **randomly selected chromosome in the selected population (before applying crossover or mutation operators)**?
- Comment on any difference in value with suitable reasoning.

---

### R5
Create **10 jobs randomly with 5 operations per job**. For each job randomly generate the **5 operation times in the range [5,50]**. The jobs need to be scheduled for **3 machines**.

Questions:
- What is the **makespan value of the chromosome with the highest fitness value**?
- How does it compare with the value chosen from a **randomly selected chromosome in the selected population (before applying crossover or mutation operators)**?
- Comment on any difference in value with suitable reasoning.

---

### R6
Reflect in **at most 3 paragraphs** the level of success that your **GA achieved in this project**.

---

# Part B Submission Requirements

Part B needs the following hand-ins:

- A **publicly accessible link to your Google Collab file** with code that covers requirements **R3, R4 and R5**.
- A **pdf file (not an image)** containing the code covering requirements **R3, R4 and R5**.
- A **separate pdf file** containing:
  - The answers to the questions asked in **R3, R4 and R5**
  - Your **reflection that covers R6**