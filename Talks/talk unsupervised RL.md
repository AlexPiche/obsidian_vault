---
theme: simple
highlightTheme: monokai

---


## Learning human objectives by evaluating hypothetical behavior

---

### Overview 

---
* We seek to **align agent behavior with a user’s objectives** in a reinforcement learning setting with unknown dynamics, an unknown reward function, and unknown unsafe states.
* We have access to a small dataset of labeled interactions.
* The reward is a categorical variable, i.e., unsafe, neutral, and good.

---
#### Illustrative Example: Trolley Problem

![[0b0584bf02449513f879837cc95f19e7e0-09-trolley.rhorizontal.w700.webp]]

---

![[Screen Shot 2022-08-03 at 12.48.36 PM.png]]
* The consequentialist and deontologist reward functions agree:
	* either one of the tracks is empty,
	* there are fewer people on the current track than the other track
---


* We start with a **generative model of initial states and a forward dynamics mode**l trained on off-policy data.
* The key idea is to actively **synthesize the hypothetical behaviors** from scratch by maximizing tractable proxies for the value of information, without interacting with the environment
---
![[KT6V02A.png]]

---

* Our method queries the user for labels at states where the **value of information is highest**
	* states where there are more people on the current track than the other track, but there are still some people on the other track.

---
### Designing Objectives for Informative Queries
---

#### Query Synthesis via Trajectory Optimization

![[Screen Shot 2022-08-03 at 1.17.00 PM.png]]

---

* **Maximizing reward.** to detect examples of false positives, or ‘reward hacking’: behaviors for which the reward model incorrectly outputs high reward.

---
* **Minimizing reward.** to augment the training data with more examples of unsafe states than would normally be encountered

---

* **Maximizing novelty.**  to produce novel trajectories that differ from those already in the training data.
---

* **Maximizing uncertainty.**  to elicit labels for examples that the model is least certain how to label, and thus reduce model uncertainty.


---
### Results

---
#### Qualitative differences between Informative Queries

 ![[Screen Shot 2022-08-03 at 1.14.39 PM.png]]


---

#### Car Racing

![[Screen Shot 2022-08-03 at 1.33.27 PM.png]]

---
#### Q1: Does synthesizing hypothetical trajectories elicit more informative labels than rolling out a policy in the training environment?

![[Screen Shot 2022-08-03 at 1.29.47 PM.png]]
###### The x-axis represents the number of queries to the user, where each query elicits a label for a single state transition (s, a, s' )
---

#### Q2: Can our method detect and correct reward hacking?

![[Screen Shot 2022-08-03 at 1.26.38 PM.png]]
###### The results on 2D navigation show that our method (orange) significantly outperforms the baselines (blue and gray).
---

#### Q3: Can our method safely learn about unsafe states?

![[Screen Shot 2022-08-03 at 1.27.06 PM.png]]

---

#### Q4: Do the proposed AFs improve upon random sampling from the generative model? 

![[Screen Shot 2022-08-03 at 1.27.48 PM.png]]

---

#### Q5: How does the regularization constant $\lambda$ control the trade-off between realistic and informative queries? 
![[Screen Shot 2022-08-09 at 9.30.22 AM.png]]


---

#### Q6: How much do each of the four AFs contribute to performance?

![[Screen Shot 2022-08-03 at 1.29.04 PM.png]]

---
## My Take-aways
* Model can be a useful tool to communicate with humans
* Uncertainty awareness is useful to not water people's time