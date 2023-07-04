---
title: "報酬決定の仕組み"
date: 2022-11-20T09:03:20-08:00
draft: false
---

[![Image from Gyazo](https://i.gyazo.com/15090778833a52122074332cb4fa7d16.png)](https://gyazo.com/15090778833a52122074332cb4fa7d16)

DeCartographyのタスクをこなすことで受け取れる報酬は、送信した回答と、あなた以外のクラウドワーカーが送信した回答によって上下します。次の文章では、具体的な例を用いて報酬決定の仕組みを解説します。

まず、クラウドワーカー（エージェント）が4人いて、各エージェントが3回、回答を送信することでタスクを実施するとします。

## Voting Weight

各エージェントがタスクに対して投票できる重み（Voting Weight）は以下の通りだとします。

- **エージェントA: Voting Weight = 1.5**
- **エージェントB: Voting Weight = 1.0**
- **エージェントC: Voting Weight = 0.8**
- **エージェントD: Voting Weight = 1.2**

実際には、Voting WeightはGitcoin Passportによるスコアと、Staking Amountをもとに決定されます。

## Total Voting Power

各エージェントのVoting Weightとタスクのセッション数を掛け合わせた値になります。
上記のエージェントたちは各々3回のセッションを実施するので、その結果は以下の通りになります

- エージェントA: Total Voting Power = Voting Weight * セッション数 = 1.5 * 3 = 4.5
- エージェントB: Total Voting Power = Voting Weight * セッション数 = 1.0 * 3 = 3.0
- エージェントC: Total Voting Power = Voting Weight * セッション数 = 0.8 * 3 = 2.4
- エージェントD: Total Voting Power = Voting Weight * セッション数 = 1.2 * 3 = 3.6

## Average Match Count

エージェント間のタスク選択の一致度を平均化したものです。この計算では、各エージェントが選んだタスクの集合が重なる度合いを比較します。
ここでは仮に、各エージェントが以下のようなタスクを選んだとします。

- **エージェントA: {Task1, Task2, Task3}**
- **エージェントB: {Task2, Task3, Task4}**
- **エージェントC: {Task5, Task6, Task3}**
- **エージェントD: {Task1, Task2, Task4}**

エージェントAのAverage Match Countを計算してみます

- エージェントAとエージェントBの選んだタスクの一致度: {Task1, Task2, Task3} ∩ {Task2, Task3, Task4} = {Task2, Task3} -> 一致したタスクは2つ
- エージェントAとエージェントCの選んだタスクの一致度: {Task1, Task2, Task3} ∩ {Task5, Task6, Task3} = {Task3} -> 一致したタスクは1つ
- エージェントAとエージェントDの選んだタスクの一致度: {Task1, Task2, Task3} ∩ {Task1, Task2, Task4} = {Task1, Task2} -> 一致したタスクは2つ

- [A, B], [A, C], [A, D]
    - {Task1, Task2, Task3} ∩ {Task2, Task3, Task4} =  {Task2, Task3} = 2
    - {Task1, Task2, Task3} ∩ {Task5, Task6, Task3} = {Task3} = 1
    - {Task1, Task2, Task3} ∩ {Task1, Task2, Task4} = {Task1, Task2} = 2

- それぞれの一致度を合計して、エージェント数-1（自分を除くエージェントの数）で割ります。
    - (2+1+2) / 3 = 1.66666667


- エージェントA: 1.66666667
- エージェントB: 1.66666667
- エージェントC: 0.66666667
- エージェントD: 1.33333333

## Distribution %

エージェントごとに「Total Voting Power * Average Match Count」の値を計算し、その後すべてのエージェントのこの値の合計で各エージェントの計算結果を割ります。

まず、「Total Voting Power * Average Match Count」の値をそれぞれ計算します：

- エージェントA: 4.5 * 1.66666667 = 7.5
- エージェントB: 3.0 * 1.66666667 = 5.0
- エージェントC: 2.4 * 0.66666667 = 1.6
- エージェントD: 3.6 * 1.33333333 = 4.8

それから、すべてのエージェントの「Total Voting Power * Average Match Count」の合計値を計算します：

- 7.5 (エージェントA) + 5.0 (エージェントB) + 1.6 (エージェントC) + 4.8 (エージェントD) = 18.9

最後に、各エージェントの「Total Voting Power * Average Match Count」の値を合計値で割り、各エージェントのDistribution % を計算します：

- **エージェントA: 7.5 / 18.9 = 0.3968 または 39.68%**
- **エージェントB: 5.0 / 18.9 = 0.2646 または 26.46%**
- **エージェントC: 1.6 / 18.9 = 0.0847 または 8.47%**
- **エージェントD: 4.8 / 18.9 = 0.2539 または 25.39%**

以上の結果から、エージェントAが最も高いRewardを得、次にエージェントB、エージェントD、そしてエージェントCの順になります。
