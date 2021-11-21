# Deep Declarative Networks

A neural network is trained via backpropagation, which generally computes gradients of each neuron w.r.t a propagated error term. However this requires a network to learn without knowledge of hard constraints and/or limits the possible functions/applications that can be used within a traditional neural network.

A Deep Declarative Network (DNN) uses implicit function theorem to extend neurons to include declarative nodes, which can be differentiated by solving an optimisation problem instead. These can be intermixed with implicit nodes (traditional non-linear neurons). In fact, functions like ReLU, sigmoid or softmax can be represented as a declarative node ([http://reports-archive.adm.cs.cmu.edu/anon/2019/CMU-CS-19-109.pdf](http://reports-archive.adm.cs.cmu.edu/anon/2019/CMU-CS-19-109.pdf)).



This approach is most notably interesting for computer vision problems, which have many existing analytical approaches. Hopefully, a DDN can utilise the known solutions for parts of a problem and learn the required solutions for other parts of a problem. This is particularly useful for many problems with have multiple individual stages to the process (some of which may often not be differentiable normally).



Original repository

{% embed url="https://github.com/anucvml/ddn" %}
Provides resources and tutorials for DDN
{% endembed %}

Blind PnP solver (uses RANSAC as a declarative node making it interesting!)

{% embed url="https://github.com/dylan-campbell/bpnpnet" %}
