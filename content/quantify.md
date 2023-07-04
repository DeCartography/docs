---
title: "How to quantify your work"
date: 2022-11-20T09:03:20-08:00
draft: false
---

[![Image from Gyazo](https://i.gyazo.com/15090778833a52122074332cb4fa7d16.png)](https://gyazo.com/15090778833a52122074332cb4fa7d16)

The rewards you can receive for performing tasks on DeCartography will vary based on the responses you submitted and the responses submitted by other crowd workers. In the following section, we will explain how rewards are determined using specific examples.

First, let's assume there are four crowd workers (agents) each of whom performs tasks by submitting responses three times.

## Voting Weight

Each agent can vote on tasks with a weight (Voting Weight) as follows:

- **Agent A: Voting Weight = 1.5**
- **Agent B: Voting Weight = 1.0**
- **Agent C: Voting Weight = 0.8**
- **Agent D: Voting Weight = 1.2**

In reality, the Voting Weight is determined based on the score from the Gitcoin Passport and the Staking Amount.

## Total Voting Power

This is the value obtained by multiplying the Voting Weight of each agent by the number of task sessions. As each of the above agents will carry out three sessions, the results are as follows:

- Agent A: Total Voting Power = Voting Weight * Session Number = 1.5 * 3 = 4.5
- Agent B: Total Voting Power = Voting Weight * Session Number = 1.0 * 3 = 3.0
- Agent C: Total Voting Power = Voting Weight * Session Number = 0.8 * 3 = 2.4
- Agent D: Total Voting Power = Voting Weight * Session Number = 1.2 * 3 = 3.6

## Average Match Count

This is an average measure of task selection matching between agents. In this calculation, we compare the overlap of the set of tasks chosen by each agent. For this example, let's assume that each agent chose the following tasks:

- **Agent A: {Task1, Task2, Task3}**
- **Agent B: {Task2, Task3, Task4}**
- **Agent C: {Task5, Task6, Task3}**
- **Agent D: {Task1, Task2, Task4}**

Let's calculate the Average Match Count for Agent A:

- Matching degree of tasks chosen by Agent A and Agent B: {Task1, Task2, Task3} ∩ {Task2, Task3, Task4} = {Task2, Task3} -> 2 tasks match
- Matching degree of tasks chosen by Agent A and Agent C: {Task1, Task2, Task3} ∩ {Task5, Task6, Task3} = {Task3} -> 1 task matches
- Matching degree of tasks chosen by Agent A and Agent D: {Task1, Task2, Task3} ∩ {Task1, Task2, Task4} = {Task1, Task2} -> 2 tasks match

Then, we add each match degree and divide it by the number of agents - 1 (number of other agents):

- (2 + 1 + 2) / 3 = 1.66666667

The Average Match Counts for all agents are:

- Agent A: 1.66666667
- Agent B: 1.66666667
- Agent C: 0.66666667
- Agent D: 1.33333333

## Distribution %

For each agent, we calculate the value of 'Total Voting Power * Average Match Count' and then divide each agent's calculated

 result by the total of this value for all agents.

First, we calculate 'Total Voting Power * Average Match Count' for each agent:

- Agent A: 4.5 * 1.66666667 = 7.5
- Agent B: 3.0 * 1.66666667 = 5.0
- Agent C: 2.4 * 0.66666667 = 1.6
- Agent D: 3.6 * 1.33333333 = 4.8

Then, we calculate the total value of 'Total Voting Power * Average Match Count' for all agents:

- 7.5 (Agent A) + 5.0 (Agent B) + 1.6 (Agent C) + 4.8 (Agent D) = 18.9

Finally, we divide each agent's 'Total Voting Power * Average Match Count' by the total to calculate each agent's Distribution %:

- **Agent A: 7.5 / 18.9 = 0.3968 or 39.68%**
- **Agent B: 5.0 / 18.9 = 0.2646 or 26.46%**
- **Agent C: 1.6 / 18.9 = 0.0847 or 8.47%**
- **Agent D: 4.8 / 18.9 = 0.2539 or 25.39%**

From these results, Agent A will receive the highest reward, followed by Agent B, Agent D, and then Agent C.