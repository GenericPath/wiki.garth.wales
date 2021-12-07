# Work Diary

#### 22/11

Initial meeting. Steve is interested in use for 3D segmentation, for this attempt will start with 2D segmentation. Masters could be doing the 3D segmentation instead.

The initial plan is to test out their code, decide if I want to use PyTorch or Tensorflow. Use deeper (or deepest) but possibly need the more powerful cards. Only one other should be using deeper currently. NeSI is always an option if needed.

Other possible areas to look into are geometric deep learning (they are interesting), light field networks (unlikely).



Main goals:

Lech: Stability of DNN (and feasibility)

Steve: 2D image segementation



#### 23/11

Installing pytorch and testing basics of the ddn framework supplied by original authors as well as Blind PnP problem ([https://arxiv.org/pdf/2007.14628.pdf](https://arxiv.org/pdf/2007.14628.pdf), [https://github.com/dylan-campbell/bpnpnet](https://github.com/dylan-campbell/bpnpnet))

#### 24/11

Going through ECCV2020 tutorial ([https://www.youtube.com/watch?v=fnJIj906qoA\&list=PLD-7XrNHCcFITANECta7DscRTC0gL2208\&index=1](https://www.youtube.com/watch?v=fnJIj906qoA\&list=PLD-7XrNHCcFITANECta7DscRTC0gL2208\&index=1)) and DDN workshop at CVPR 2020 ([https://www.youtube.com/playlist?list=PLD-7XrNHCcFJCxYrZQRYsTvv3mTogWiiI](https://www.youtube.com/playlist?list=PLD-7XrNHCcFJCxYrZQRYsTvv3mTogWiiI))

#### 25/11 - 26

Going through codebase and pytorch



#### 29/11

Answer for what has been done before 43:15 https://www.youtube.com/watch?v=pRbxXlvj4SA\&list=PLD-7XrNHCcFITANECta7DscRTC0gL2208\&index=7

DDN works well as we dont need to unroll the whole function, and store all the intermediate steps. Implicit differentiation works well as we only need the ends? Also lets you try out different solvers, without implementing them in pytorch. Unrolling also may lead to more floating point errors, which an analytical solution will not need.

Go through image segmentation techniques, see how it might work.



#### 30/11

Learnt about image segmentation ([https://en.wikipedia.org/wiki/Graph\_cuts\_in\_computer\_vision](https://en.wikipedia.org/wiki/Graph\_cuts\_in\_computer\_vision), [https://en.wikipedia.org/wiki/Watershed\_(image\_processing)](https://en.wikipedia.org/wiki/Watershed\_\(image\_processing\)), [https://hal.archives-ouvertes.fr/hal-02063210v2/document](https://hal.archives-ouvertes.fr/hal-02063210v2/document))

Neural network could learn the (dis)similarity function? and include the K-means style approach as a declarative node) This could learn how to best distinguish unique segments, and then learn to output it.



Meeting: Essentially the above style of approach.

Image -> dissimilarity neural network -> graph cut (declarative node) -> oversegmented graph? -> labelling / clustering.

Start with output of pure labelling. And utilise a multi-stage network as a baseline. Compare the full, multi-stage and fixed dissimilarity approaches (e.g. typical approaches for intensity, colour etc)



Also determine stability and how RANSAC works in a system.



\----

#### 6/12

Possibily create something for explicitly testing stability of a network

Use small images so memory constraints aren't bad.. just want to test it works really.



#### 7/12

Papers for pixel wise image segmentation in machine learning

[https://arxiv.org/pdf/1901.11390.pdf](https://arxiv.org/pdf/1901.11390.pdf)\
[https://arxiv.org/pdf/1706.05587.pdf](https://arxiv.org/pdf/1706.05587.pdf)\
[https://arxiv.org/pdf/1608.06993.pdf](https://arxiv.org/pdf/1608.06993.pdf)\
[https://arxiv.org/pdf/1505.04597.pdf](https://arxiv.org/pdf/1505.04597.pdf)
