---
title: "DeCartography: Building a Credible Neutrality Social Graph powered by Web3 Crowdsourcing"
date: 2022-11-20T09:03:20-08:00
draft: false
---

[![Image from Gyazo](https://i.gyazo.com/9e1135342b24fb94d3ee9c5b9b64f183.jpg)](https://gyazo.com/9e1135342b24fb94d3ee9c5b9b64f183)

DeCartography is a Relational Computation Oracle that leverages Web3 crowdsourcing, providing a social graph while maintaining Credible Neutrality.

By using this oracle, it is possible to quantify collaboration and social distance as a social graph.

Currently, we provide a social graph as an infrastructure for Plural QF, analyzing the data of Gitcoin's Gitcoin Citizens Round #1 as a Proof of Concept.
→[Round1](Round1.en.md)

There are existing social graph providers that also "analyze given data, create a social graph, and provide the results to other apps," but what sets DeCartography apart is the adoption of complex system over a mathematical approach in the analysis process.

The former requires pre-defined measurement criteria due to its nature of being "analysis," which relies on mathematical methods. In contrast, DeCartography avoids the necessity of **specific indicators for generating social graphs** by employing crowdsourcing and [peer prediction method](https://pubsonline.informs.org/doi/abs/10.1287/mnsc.1050.0379), enabling data analysis based on Schelling points.

- **As an oracle user**: If you have data you want to analyze, send that data with the necessary fee to the DeCartography platform. After a certain period, the analyzed data will be returned. Currently, in beta version, we are mainly analyzing the data of projects that have contacted us.

- **As a Crowd-worker**: By solving tasks posted by DeCartography as a cloud worker, you can earn cryptocurrency without the need for KYC. Sign in to DeCartography using your wallet, complete the task, wait for the specified period, and the reward will be automatically transferred.

<br>

## Key Features

- Consensus mechanism as a Relational Computation Oracle: In Web3 crowdsourcing, when there is no ground truth, by defining as a distributed oracle using the Schelling point mechanism, it solves the problem of not having a metric to determine the rewards for cloud workers acting as validators. This concept revolves around the idea of "multiple entities defaulting to a common solution to a problem when there is no communication."

- Prevention of Sybil Attacks: Prevents Sybil attacks using Gitcoin Passport and optional staking before starting a task.

- Quantification of each Crowd-worker's work (reward calculation): The reward calculation for each Crowd-worker uses a peer prediction method that determines rewards based on the correlation of each agent's answers.

- Distribution of rewards: Rewards are distributed a certain period after working on the task through batch operations for transfers.
<br>

---

<br>

https://decartography.com/
