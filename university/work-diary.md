---
description: All work and no play makes jack a dull boy
---

# Work Diary

### Week 5

**31/03 - Wednesday**   
Started the 420 assignment, setup CUDA on local pc.

**2/04 - Friday**   
Created Notion planning website. Started summarising papers. Setup the lab computer and got remote access setup.

### Week 6 \(Easter break\)

**6/06 - Tuesday**

Working out which methods I want to use  
[i.e. looking at A Comparison of Reinforcement Learning Frameworks: Dopamine, RLLib, Keras-RL, Coach, TRFL, Tensorforce, Coach and more](https://winderresearch.com/a-comparison-of-reinforcement-learning-frameworks-dopamine-rllib-keras-rl-coach-trfl-tensorforce-coach-and-more/)  
  
Stable baselines still has the best implementation of everything, but looks hardest to work with.

**11/04 - Sunday**  
Switch to gitbook, summarising papers more.

### **Week 7**

**12/04 - Monday**  
Started implementing keras-rl, gave up on using stable-baselines. Stable-baselines just lacks the easy interoperability with tensorflow how I wanted it to... or I don't understant how gym works :\)

**13/04 - Tuesday**  
Realised Keras-RL is dead, therefore should replace with something with complete documentation. [Most RL frameworks ](../ml/rl-frameworks.md)act similarily as they use [Gym ](../ml/gym.md)style environments. _Also working on other ai_ _assignment._

_~~ I got distracted by assignments ~~_

### **Week 9**

**5/05 - Wednesday**  
Supervisor meeting: Store all possible permutations of an image \(zoom, shift etc\) and then feed the CNN features into the model, instead of images. Spend a day to calculate all the features so the training process is quicker. Another point, eventually use continuous action space rather than discrete. e.g. zoom levels and move left/right by a chosen amount. Discrete is making it learn more easily, but continuous might let it bet other systems.

**6/05 - Thursday**  
Switched to rllib instead of stable-baselines, because sb2 is outdated. rllib seems to make more sense too for implementing custom models. Some reddit threads suggested it or sb3 but sb3 is pytorch only.

**10/05 - Monday**  
Fully working 'step' for the environment. Observations need to be implemented.

\_\_

