---
title: "Challenges"
date: 2022-11-20T09:03:20-08:00
draft: false
---

We know that building a distributed oracle like DeCartography has many challenges, including withstanding various hacks, not being dominated by a simple majority, and having a skewed community of contributors (crowd workers).

We have been publicly building DeCartography since Jun 24-26, 2022 and are designing it while seeking input from the broader community.

Here are a handful of particular challenges we are aware of as well as steps we are taking to address them:

## Prevention of tampering
Collaborative hacks (collusion) are a significant risk to open rating systems, and in order for DeCartography's social graph to be effective, such attempts must be countered.

Currently, the program takes multiple steps to reduce the likelihood of such manipulation.

* All cloud workers will be required to sign in with Gitcoin Passport. (Beta version uses Google sign-in) This is a consolidation of multiple 1 person, 1 ID protocols, which allows the business to ensure 1 person, 1 ID.

* These standards are in place to prevent the creation of large numbers of fake or disguised crowdworker accounts that could be used for fraudulent evaluations.


* Second, DeCartography is not a majority-supported answer mechanism like many engagement-based ranking systems. Instead, it will use the [peer prediction method] (not yet implemented in the beta version)

* For a person's answer to have a significant impact, people in different clusters must also agree.

* Academic studies have shown that such bridging-based ranking can help identify healthier, higher quality content and reduce the risk of elevating biased content.


* Newer accounts with a track record of quality contributions to responses will have a higher Commonsense Score, and newer accounts that do not yet have a track record of responses will have a lower Commonsense Score; the compensation DeCartography pays for end-user work is determined according to this "commonsense"; the higher the Commonsense Score, the more likely the account will be to receive a higher score.

## Feedback? Ideas?
We welcome your feedback on these and other risks and challenges, as well as ideas for addressing them, please contact us via DM @DeCartography.
