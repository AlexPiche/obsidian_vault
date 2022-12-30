---
title: General Policy Evaluation and Improvement by Learning to Identify Few But Crucial States
authors: Francesco Faccio, Aditya Ramesh, Vincent Herrmann, Jean Harb, Jürgen Schmidhuber
year: 2022
tags:
  - DataCentric
  - RL
---

![[Screen Shot 2022-08-05 at 11.47.22 AM.png]]
* In continuous control problems with infinitely many states, our value function minimizes its prediction error by simultaneously learning a small set of ‘probing states’ and a mapping from actions produced in probing states to the policy’s return.
* Surprisingly, it is possible to clone the behavior of a near-optimal policy in Swimmer-v3 and Hopper-v3 environments only by knowing how to act in 3 and 5 such learned states, respectively.
* ![[Screen Shot 2022-08-05 at 11.53.30 AM.png]]