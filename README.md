# Cutting Stock Problem Using Simulated Annealing

## Introduction

The Cutting Stock Problem is a challenging optimization problem that arises in various industries, including paper manufacturing and sheet metal production. The goal is to cut standard-sized rolls or sheets of material into smaller pieces of requested sizes while minimizing material waste. This problem is known to be NP-hard, making it computationally complex.

In this project, we slove the Cutting Stock Problem with the following scenario: We have a paper machine that can produce an unlimited number of master rolls, each with a width of `c` meters. We also have a set of cut requests that specify the required lengths of the smaller pieces. Our objective is to find an optimal way to cut the rolls to fulfill all requests while using the minimum number of rolls.

## Problem Statement

For instance, let's consider a scenario where we have ten-meter paper rolls and receive requests for pieces of 3, 5, and 7 meters. One of the optimal solutions to this example involves using only two rolls, with minimal waste.

- Roll 1: 5 meters + 3 meters (2 meters of waste)
- Roll 2: 7 meters (3 meters of waste)

## Input Data

The input data for the problem is provided in a file named `input1.stock`. It contains information about the available stock length (`stock_Length`), temperature (`T`), and a predefined cost limit (`cost`). Additionally, it lists the cut requests as a comma-separated list.

## Solution Overview

### Initialization

1. Read the input data from the file and parse it to extract the stock length, temperature, cost limit, and cut requests.

2. Initialize a population of potential solutions. Each solution represents a permutation of the cut requests.

### Fitness Function

3. Define a fitness function that evaluates the quality of a solution. It calculates the number of rolls needed to fulfill all cut requests for a given permutation.

### Neighborhood Generation

4. Create a neighborhood generator that explores neighboring solutions. It swaps two random cut requests in the permutation to generate a new solution.

### Simulated Annealing

5. Implement the Simulated Annealing algorithm to explore the solution space efficiently. The algorithm iteratively searches for better solutions and accepts less optimal solutions with a decreasing probability, controlled by the temperature function.

### Termination

6. Continue the search until the fitness (number of rolls used) is less than or equal to the predefined cost limit.

### Output

7. Print the optimal solution, including the number of rolls used and the allocation of cut requests to each roll.

## Performance Enhancements

In this implementation, the goal is to find solutions that use fewer rolls than the predefined cost limits. To enhance the code's performance, the Simulated Annealing algorithm is utilized to efficiently explore the solution space.

### Temperature Function

The temperature function (T) is responsible for controlling the acceptance probability of less optimal solutions. The adjustment of the temperature function is aimed at gradually decreasing the probability of accepting worse solutions, thereby allowing the algorithm to converge towards an optimal solution.

### Neighborhood Exploration

Exploration of neighboring solutions involves the random swapping of two cut requests in the permutation. This method introduces diversity and aids the algorithm in escaping local optima.

