---
description: All work and no play makes jack a dull boy
---

# Work Diary

note to self: write these discussing every little concern, problem and solution found throughout the year.

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

### Week 10

**10/05 - Monday**  
Fully working 'step' for the environment. Observations need to be implemented.

**11/05 - Tuesday**  
Will switch rl library, rllib is just painful but so are most. Narrowed down a list of libraries to use.. keras-rl has a replacement that looks good or Acme which is designed more around my purpose \(tf.dataset\)

**12/05 - Wednesday**  
Acme, dopamine are all weird. Tensorforce lets you split the problem apart, but after meeting I might not switch to that...   
Supervisor meeting: don't bend the RL, bend the problem to fit RL. RL should be blind to the problem. So best practice may be to make the environment consist of all the images, and reset\(\) doesn't reset to the same image, but to a random image from all the images. This way an episode could be a lot of images all in one. It is being presented with a series of images that it is trying to localise within.

**13/05 - Thursday**  
Setting up stuff for the downloaded dataset and environment to choose random images per reset  
JC paper never talks about how the train/test separation occurs. Rewards are only relevant for training is the only thing mentioned \(if so, what do you do instead?\) JC paper never mentions how it handles finishing with no moves or with some moves \(are these separate potential choices? or a single decision?\)

 **14/05 - Friday**  
_Steve's thesis writing seminar_    \(to be a better writer you need to read and write.\)  
  
 - Write down what makes certain papers easy to read  
- Write down what makes it harder to read  
  
Don't just copy the bad academic writing, find the ones that make sense and copy their style.  
Don't expect the writing to be perfect first time, just write a bunch of rubbish and edit it all.  
The supervisor can't write it, but can make big edit suggestions!  
  
If you can explain it verbally you can write it down \(could consider transcribing stuff\)  
You aren't writing a murder mystery, but you want some 'story'  
as above, so the summary/abstract tells the full story in short \(the butler did it this is what we used to find out\)  
  
Full examples \(showing all the steps\) make it easier to understand. Like in JC paper they don't explain every single step but just talk about oh these things happen but don't cover all the cases.  
  
Things that annoy  
- overcomplicate \(makes you feel smart, but we want to make reader feel smart\)  
- jargon / TLAs \(three leter acronym\)  
  
Can't explain everything, have to assume some level of knowledge \(especially if journal has page limit\)  
You want images to float around, but don't want to create gaps of whitespace \(makes it seem like the end of the chapter\)  
  
Number equations! And use syntax with them \(i.e. if something becomes x=123123. or matrix, X=\[\], where..\)  
  
Numbered references make sense for small works, but a PhD with 120 pages and 200 references \[137\] isn't going to be useful, instead \(V Minh et. al, 2015\)  
  
Write early, write often  
- You'll forget stuff, get feedback earlier, writing is not just words as well \(figures, references, ideas, questions, data/results/timings\) Use something like this to keep track of it all!  
  
Project report  
- Medium sized document, sections but not chapters  
- Need to organise ideas  
- Need to worry about 'story'  
  
Typical structure is good \(won't confuse the markers! but not the only option\)  
- Introduction  
- Background / related work  
- Methods / approach  
- Results and analysis  
-Discussion and future work  
- References / bibliography  
- Appendices  
Slides on typical structure are good  
Related work, boring if you just say 'x did \_\_'.  
- Instead organise, analyse and give insight. \(The main approaches are.., 'gap' to address\)  
 \(4th year we can just replicate but i'm kinda trying to improve\)  
No is a perfectly acceptable answer if you know it really didn't work and why it didn't work  
Say the results in abstract, introduction, results and conclusion \(marker might notice them this way!\)  
  
Things that don't help the writing  
- complaining about libraries or getting compiler to work \(not interesting to the reader!!\)  
Target audience should be 4th year computing \(someone not in your area!\)  
  
Looking for  
- how much you learnt, how much you know about the area  
  
Explain all the terms \(i.e. what is a convolutional neural network the first time you use it\)  
- Someone in computer science doesn't neccessarily know what it is or might need a refresher  
- Same word might mean one thing and something else to someone else, define these and be consistent with meaning  
  
Keep it simple! Not utilize but use, not learnings but lesson. Don't become all 'academic'.  
Don't need to say deploy a developed implementation, you aren't going to deploy a non developed implementation. Remove words that aren't doing anything. ENGL127 lessons.  
  
"If you wouldn't say it, don't write it" \(but the converse isn't true\)  
Read the writing aloud to see how natural it is. \(Need to break it up also to breathe\)  


