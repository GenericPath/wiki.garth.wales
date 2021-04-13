---
description: >-
  OpenAI's way to create a reinforcement learning environment, used by most RL
  implementations.
---

# Gym

* [ ] TODO: Further my understanding of OpenAI's Gym

Gym seeks to create standard environments, enabling better benchmarks to drive research in reinfrocement learning.

An environment contains:

* action\_space: space object corresponding to valid actions
* observation\_space: space object corresponding to valid observations
* reward\_range: corresponding min and max possible rewards

A step in an environment contains:

* observation \(object\): pixel data, angles, velocities or board states
* reward \(float\): amount of reward achieved by previous action
* done \(boolean\): whether to reset the environment, termination action.
* info \(dict\): diagnositic information \(i.e. raw probabilities for last state\)

![The framework of reinforcement learning](https://gym.openai.com/assets/docs/aeloop-138c89d44114492fd02822303e6b4b07213010bb14ca5856d2d49d6b62d88e53.svg)



* How to create custom environment: [https://gym.openai.com/docs/\#environments](https://gym.openai.com/docs/#environments)
* Keras-RL uses gym style environments \(although the included ones are [blank abstract classes](https://keras-rl.readthedocs.io/en/latest/core/)\) 

