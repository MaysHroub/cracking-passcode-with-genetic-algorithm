# Cracking the Code with Genetic Algoithms 🧬

This project implements a genetic algorithm (GA) in Python to crack a hidden 32-bit binary passcode. The goal is to find the passcode by evolving a population of candidate solutions (chromosomes) through several generations using techniques such as selection, crossover, mutation, and elitism.

The project is part of the AI course at Birzeit University (2024).

## Table of Contents
- [Problem Formulation](#problem-formulation)
- [Algorithm Explanation](#algorithm-explanation)
- [Key Parameters](#key-parameters)
- [Chromosome and Gene Representation](#chromosome-and-gene-representation)
- [Parameter Tuning](#parameter-tuning)
- [Author's Note](#authors-note)

## Problem Formulation

Our objective is to discover a hidden 32-bit binary sequence, known as the Passcode. This is framed as an optimization problem where the goal is to maximize the fitness score of candidate solutions.

We must implement the algorithm from scratch, without using external libraries.

### Approach:
- **Chromosome Representation:** Each chromosome is represented as a 32-bit binary string, where each bit is a gene.
- **Fitness Evaluation:** Fitness score is calculated by comparing the chromosome with the target passcode. The fitness score is the number of bits that match the passcode.
- **Selection:** Parents are selected based on their fitness scores. Tournament selection is used to choose the best parents for reproduction.
- **Crossover:** Parents undergo crossover to produce offspring (new solutions).
- **Mutation:** Offspring undergo mutation to introduce some randomness and prevent the algorithm from getting stuck in local optima.
- **Elitism:** The best individuals are carried forward unchanged into the next generation.
- **Stopping Condition:** The algorithm stops when:
  - The passcode is found (fitness score of 32).
  - The maximum number of generations is reached.

### Note:
There are two types of mutation:

**1. Chromosome-Level mutation**

In chromosome-level mutation, we decide whether to apply mutation to the whole chromosome. If mutation is applied, random bit(s) is/are picked and inverted (fliped).

**2. Population-Level mutation**

In population-level mutation, we decide whether to apply mutation to some individuals in the entire population. If mutation is applied, it affects the whole chromosome.


## Algorithm Explanation
The genetic algorithm works as follows:

1. **Initial Population Generation:** Start by generating a random population of chromosomes. These chromosomes serve as potential solutions.

2. **Fitness Evaluation:** Each chromosome's fitness is evaluated by comparing it to the target passcode. The fitness score is the number of bits that match the passcode.

3. **Parent Selection:** Tournament selection is used to choose parents for the next generation. The best chromosomes are more likely to be selected.

4. **Crossover and Mutation:** Crossover combines two parent chromosomes to create offspring, and mutation randomly changes some of the offspring's bits to introduce diversity.

5. **Elitism:** The top elite chromosomes are carried over to the next generation without any changes, ensuring that the best solutions are not lost.

6. **New Generation:** A new generation is created by combining the offspring and the elite individuals. This process is repeated until a perfect solution is found or the generation limit is reached.


## Key Parameters
The performance of the genetic algorithm depends on several key parameters:

1. Population Size: Defines the number of individuals in each generation. A larger population size may improve genetic diversity but increases computational demands.

2. Crossover Rate: Determines the probability of crossover between two parents. A higher rate facilitates exploration of the solution space.

3. Mutation Rate: Defines the probability of mutation for each gene. A suitable mutation rate helps maintain diversity within the population.

4. Tournament Size: Refers to the number of individuals randomly chosen for selection in each tournament. The one with the highest fitness is selected as a parent.

5. Elite Size Rate: Specifies the proportion of the best individuals that are carried over to the next generation unchanged.



## Chromosome and Gene Representation

### 1. Chromosome 
A chromosome is represented as a 32-bit binary string. Each chromosome is a potential solution to the problem, and its fitness is evaluated based on how closely it matches the target passcode.

#### Example:
Target passcode: 10010101111110100001100001000111
Chromosome: 10010101111110100001100001000111 → Fitness: 32 (Perfect match)

### 2. Gene 
A gene is a single bit within the chromosome. Each bit (0 or 1) is compared with the target passcode. The closer the chromosome gets to the passcode, the better its fitness score.

#### Example:
Chromosome: 11000101111110100001100001000110
Fitness = 28 (matches 28 bits of the target passcode)



## Parameter Tuning
To optimize the algorithm’s performance, we experimented with different values of the key parameters:

- Population Size: Larger population sizes enhance genetic diversity but come at a higher computational cost.

- Crossover Rate: A higher crossover rate allows for more exploration of the solution space.

- Mutation Rate: Proper mutation rates prevent the population from becoming stagnant.

- Tournament Size: Tournament selection ensures that the fittest individuals are selected to propagate.

- Elite Size Rate: Preserving elite individuals guarantees that the best solutions are retained.



## Author's Note (。・∀・)ノ

Although, my laptop got cooked while running the program and I also recived a horrible grade, the project was fun to make :3

Plus, if there's any problem or incorrect information, please feel free to contact me or create an issue. <3


