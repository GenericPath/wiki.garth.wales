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
- Someone in computer science doesn't necessarily know what it is or might need a refresher  
- Same word might mean one thing and something else to someone else, define these and be consistent with meaning  
  
Keep it simple! Not utilize but use, not learnings but lesson. Don't become all 'academic'.  
Don't need to say deploy a developed implementation, you aren't going to deploy a non developed implementation. Remove words that aren't doing anything. ENGL127 lessons.  
  
"If you wouldn't say it, don't write it" \(but the converse isn't true\)  
Read the writing aloud to see how natural it is. \(Need to break it up also to breathe\)

**Friday cont**  
Consider adding random noise / data augmentation like in normal things... for real world applications this could be useful but for Atari it didn't seem to improve it \([https://www.youtube.com/watch?v=fevMOp5TDQs](https://www.youtube.com/watch?v=fevMOp5TDQs)\)  
Running environment on the Atari CNN policy... will implement the real one tomorrow?

~~~~ Doing assignments ~~~~

**31/05 - Monday**  
Working on getting some results from the model.  
This link is useful [https://andyljones.com/posts/rl-debugging.html](https://andyljones.com/posts/rl-debugging.html)

**1/06 - Tuesday**  
The default settings for stable-baselines DQN is similar to the papers settings... Trying some different models. One of the previous models \(features\_mlp\_4\) actually does demonstrate it has learnt. But it struggles with the final part of 'ending'. I may need to try a lower gamma or more training time.

**2/06 - Wednesday**  
Supervisor agreed it seems like an appropriate set up to learn. May need to train for longer. The only weird part is training on a single image resulted in worse performance. If anything it should be able to memorise instead of learn yet it just does bad behaviour. Sanity checks seem to hold true so who knows... Maybe I need to write some unit tests? Maybe.. Will start training and writing the report.  
Also Lech suggested exponential reward scheme as opposed to linear \(current +1+1-1 linear\)  
  
I also learnt about how reinforcment learning algorithms work..  
[https://stats.stackexchange.com/questions/355820/why-do-temporal-difference-td-methods-have-lower-variance-than-monte-carlo-met](https://stats.stackexchange.com/questions/355820/why-do-temporal-difference-td-methods-have-lower-variance-than-monte-carlo-met)  
[https://old.reddit.com/r/reinforcementlearning/comments/bb64ui/why\_not\_just\_accumulate\_all\_the\_future\_rewards/](https://old.reddit.com/r/reinforcementlearning/comments/bb64ui/why_not_just_accumulate_all_the_future_rewards/)  
Also should make definitions of all the statistical terms that I don't neccessarily remember fully.  
  
Both TD and MC use the same formula for RL for action value estimation...  
But Monte carlo changes estimations based on sums of steps \(biased!\)  
where as TD changes estimations based on single step changes \(un-biased\)  
 TD uses bootstrapping to let it actually do something \(this is the period of before learning starts.. this way it will learn a bias representation at the start just to boostrap the actual learning. the actual learning will slowly debias this  
  
Also this is interesting [https://aakash94.github.io/Reward-Based-Epsilon-Decay/](https://aakash94.github.io/Reward-Based-Epsilon-Decay/)  
\(Maybe Rainbow already implements this?\)  
  
Also from the above reddit thread  
"The bias/variance trade-off is not obvious in N-step DQN. When N increases, on one hand you decrease the bias because you use additional "real" rewards \(and reduce the weight of the bootstrapped component\), but on the other hand you also increase the bias due to the fact that you are working off-policy \(those "real" rewards were obtained when following an old version of your policy\). So the end result in unclear and will depend on your specific setup \(in practice it seems that it often helps to use a small N &gt; 1, e.g. between 3 and 5\)."  
So essentially that is what the steps between learning is?

**3/06 - Thursday**  
Continued working on the program. Downloaded widerface and FDDB datasets as the original dataset had only 472 images with only one face \(the training can't neccessarily handle more at the moment..\)  
PASCAL VOC compared to say ImageNet is that it will likely have more objects in a given scene, therefore will enable it to distinguish things in one scene.  
[https://tuggeluk.github.io/papers/preprint\_deepscores.pdf](https://tuggeluk.github.io/papers/preprint_deepscores.pdf)

**4/06 - Friday**  
Buffer size depends on how much you want to learning based on recent actions vs historical actions.  
Too big and it will not learn quickly as it is learning from experiences with an old network, too small and it will be able to take note of the most recent experiences.  
[https://acsweb.ucsd.edu/~wfedus/pdf/replay.pdf](https://acsweb.ucsd.edu/~wfedus/pdf/replay.pdf)  
[https://ai.stackexchange.com/questions/11640/how-large-should-the-replay-buffer-be](https://ai.stackexchange.com/questions/11640/how-large-should-the-replay-buffer-be)  
[https://ai.stackexchange.com/questions/13289/are-neural-networks-prone-to-catastrophic-forgetting/13293\#13293](https://ai.stackexchange.com/questions/13289/are-neural-networks-prone-to-catastrophic-forgetting/13293#13293)

**11/06 - Friday**  
Writing about neural networks and convolutions.. [https://chriswolfvision.medium.com/what-is-translation-equivariance-and-why-do-we-use-convolutions-to-get-it-6f18139d4c59](https://chriswolfvision.medium.com/what-is-translation-equivariance-and-why-do-we-use-convolutions-to-get-it-6f18139d4c59)  
[https://cs231n.github.io/convolutional-networks/](https://cs231n.github.io/convolutional-networks/)  
  
Note: Pooling is bad for face recognition, because it removes the spatial information for distance between eyes etc... +features, it seem, are very inprecise currently \(i dont know how true that is though\)

**14/06 - Monday**  
[https://lilianweng.github.io/lil-log/2017/12/31/object-recognition-for-dummies-part-3.html\#fast-r-cnn](https://lilianweng.github.io/lil-log/2017/12/31/object-recognition-for-dummies-part-3.html#fast-r-cnn)  
Working on background..  
[https://towardsdatascience.com/r-cnn-fast-r-cnn-faster-r-cnn-yolo-object-detection-algorithms-36d53571365e](https://towardsdatascience.com/r-cnn-fast-r-cnn-faster-r-cnn-yolo-object-detection-algorithms-36d53571365e)

  
  
  


 

  


