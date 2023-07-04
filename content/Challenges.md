---
title: "Experiments as DeCartography"
date: 2022-11-20T09:03:20-08:00
draft: false
---

We recognize that there are many challenges in building a decentralized oracle like DeCartography, including resilience to various hacking and manipulation, not being dominated by a simple majority, and issues such as the Crowd-worker community being biased.

We have been building DeCartography as an open-source project since June 24, 2022, and designing it while seeking opinions from a broader community.

Below are specific challenges we recognize and steps to address them:

Attack-vector (Sybil attacks, collusion) is a significant risk for open evaluation systems, and DeCartography's social graph must counter such attempts to be effective.

We are currently taking several measures to reduce the possibility of such fraudulent manipulation:

- **All Crowd-workers are required to sign in with [Gitcoin Passport](https://passport.gitcoin.co/)**. This is an integration of several 1Person, 1ID protocols, which can receive the uniqueness of the Crowd-worker as a Humanity Score. This allows DeCartography to reduce the risk of Sybil attacks.

- DeCartography is not a mechanism that determines by majority vote support like a ranking system. Instead, it uses [peer prediction method](https://pubsonline.informs.org/doi/abs/10.1287/mnsc.1050.0379).

- For a Crowd-worker's answer to have a significant impact on the data it generates, Crowd-workers thought to belong to a different community from the individual must also agree.

Such bridging-based mechanisms have been shown in academic research to help capture higher quality responses and reduce the risk of a single community banding together to manipulate the oracle's results.

Crowd-workers with a track record of submitting high-quality responses have a high Common Sense Score, while new Crowd-workers without response track record (haven't completed many tasks) have a low Common Sense Score.

The rewards DeCartography pays to end users for their work are determined according to this "common sense." The higher the Common Sense Score of an account, the higher the potential to receive higher rewards. For more details, please see the mechanism of reward determination.

We welcome feedback on these risks and challenges, as well as ideas to address them.