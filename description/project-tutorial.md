# Project 2 Discussion Document
Artificial Intelligence – Spring 2026

Overall Strategy

Schedule at the job level, not at the operational level. This is called the permutation schedule.

The permutation schedule is the same for all machines – this will ensure that no deadlock will take place.

Algorithm 1: Applying the GA to the Job Shop Scheduling Problem

Generate a total of 120 permutations. You may call the permutations(range(N)) method for this, with N set to 5. Each permutation is referred to as a chromosome and represents the order in which the jobs are run. This is the initial population P.

For each chromosome in P compute its fitness value fi (see details on this that appear later). The fitness value for chromosome i is the time taken to execute the set of jobs with chromosome i (see algorithm for computing the makespan below).

Select M (=10) chromosomes from P according to the following probability.

Perform the crossover operation for all 45 pairs amongst the 10 chromosomes selected in step 3.

Now apply the mutation operation to these 45 new chromosomes with a 5% probability.

Compute the fitness value of the new chromosomes and add them to the population.

Repeat steps 3 to 6 for 99 more iterations, thus yielding a total of 100 generations.

Extract the job schedule of the chromosome having the highest fitness value from the population. Report its fitness value as the makespan.

Schedule Evaluation

Suppose that we have 5 jobs, each with two operations of their own.

Job #
Op1 Time
Op2 Time

1
3
6

2
10
1

3
3
2

4
2
4

5
8
8

Table 1: Job Specification for R3

Suppose that we have a job schedule of 4, 1, 5, 3, 2 then we can compute the makespan of this schedule as follows:

J41   0        2  M1
J42        2        6  M2

J11        2        5  M1
J12            6       12  M2

J51            5           13  M1
J52                13       21  M2

J31                13       16  M1
J32                    21       23  M2

J21                                16       26  M1
J22                                    26       27  M2

This value of 27 as the makespan is the optimal (least) value that can be obtained for the jobs given in Table 1.

Computation of schedule makespan (M)

The makespan is the fitness value and it equals the time of completion of the last job that was scheduled.

Set M = EJ41 = 2

Update M as follows:

Take the next pair of operations that are scheduled in parallel until the last operation of the last scheduled job. Suppose these operations are A and B.

Update the value of M so that M = max(EA, EB) where EA, EB refer to the end points of operations A and B.

Finally add on the last operation time (1) to M.

M = M + 1

This will give a value of 27 for the given job schedule

Implementing the crossover operation

We will use a more effective form of crossover than the single point crossover which is commonly used. This method uses an interval, rather than a single point. It works as follows:

Two cutting sites are chosen randomly:

parent 1   1 2 3 |4 5 6| 7 8 9
parent 2   7 6 9 |4 3 2| 1 5 8

Divide the parents into 3 substrings s1, s2 and s3. The substring s2 is the cross-section region (the area situated between the two cutting sites).

The symbols that appear in parent 1’s cross-section is removed from parent 2 leaving some "holes" (showed with H)

parent 2   7 H 9 |H 3 2| 1 H 8

Copy the letters in s2 to child 1. This will result in *** 456 *** for child1 (* is a letter that can take any value; it will be filled in later)

Now simply copy from parent 2 to child 1 ignoring any holes H. This will give: 7 9 3 |4 5 6| 2 1 8 for child 1

Child number 2 is obtained with a symmetrical process.

child 1     7 9 3 |4 5 6| 2 1 8
child 2     1 5 6 |4 3 2| 7 8 9

Implementing the mutation operation

This is quite simple. For each chromosome, swap with a certain probability (which is 5% in our case) two randomly selected positions in the chromosome.

7 9 3 4 5 6 2 1 8
      ^        ^

After swapping the chromosome mutates to:

7 9 1 4 5 6 2 3 8