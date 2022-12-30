# Prior over reward functions

* humans have different preferences
* We may be able to specify a prior over these preferences
* We can train an agent to maximize each of these preferences, once conditioned on one.
* At test time, we can try to infer the human preferences

# Diffusion for preference
* Learn a diffusion model to go from a behavior with lower preference to one with higher preference [[@baiTrainingHelpfulHarmless2022]]

# Learning "Unit tests"
* Dialog systems: learning dangerous prompts
* RL: learning critical states