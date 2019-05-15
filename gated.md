---
layout: default
title: A Brief Summary of Gated-Attention Architectures for Task-Oriented Language Grounding
---


**A Brief Summary of Gated-Attention Architectures for Task-Oriented Language Grounding**

[A link to the original paper](https://arxiv.org/abs/1706.07230)



**What is it about**

-
  -
    - Mapping instructions to objects is called task-oriented language grounding
    - Proposal

-
  -
    -
      - End-end trainable architecture handling raw pixel input for TOLG in 3D(show that model performs well over unseen instructions and maps)
      - Develop gated\_attention mechanism for multimodal representations of verbal instructions and visual elements. Performs better than concatenation method. Done over various policy learning methods
      - Introduce new 3D env built with game engine with actions, objects and their attributes
    - Model- Combines visual elements and text representations using Gated-Attention mechanism and learns policy to execute instructions using standard RL and imitation learning methods. Input for the model is raw pixels and NL instructions
      - Model consists of State Processing Module, Policy Learner
      - Model is tested on unseen maps and instructions
      - Model is trained on a 3D environment created using a gaming engine
    - Challenges:
      - Learn to recognize object from raw pixel
      - Explore environment(occlusion of objects)
      - Ground each concept of instruction in visual element
      - Ground action in environment
      - Understand the pragmatics of language(superlatives etc)
      - Navigate env while avoiding incorrect objects
    - Problem Formulation

-
  - Episode terminates when any object is reached or episode time up
  - NL instruction-L
  - Action- a
  - Image- I
  - Episode- ∈
  - State- S function of (I,L)
  - Policy- π function of (a,s) at time t- action for that state. Objective of policy to reach correct object within episode time. RL and imitation learning approaches used and contrasted for performance

**Approach**

-
  -
    - State Processing Module-creates joint representation of instructions and images observed by agent. Two types of joint representation

-
  -
    -
      - Concatenation-used by previous papers
      - Gated-attention multimodal fusion- prefered method in this paper-multiplicative interactions between modalities.
      -
      - Takes current state as input st = {It,L}
      - Consists of CNN to process image        xI = f (It ; θconv ) ∈ Rd×H ×W. D-feature maps, h,w height and width of each feature map. θconv the configuration of the CNN.
      - GRU network to process instructions Let xL = f(L;θgru). Θgru Parameters of GRU network.
      - Multimodal fusion unti to combine both        image and instruction M(xI,xL)
      -
      - Fusion Through GRU
      - Intuition of GRU is CNN will detect certain features of the visual object and gates relevant features according to instruction aL
      - xL is passed through fully-connected linear layer with sigmoid activation .O/p dimension of linear layers equals number of feature maps-d- in o/p of CNN(image)
      - Output is aL = h(xL ) ∈ Rd called attention vector
      - Each element in aL is expanded in HxW resulting in a 3-dim matrixM(aL) ∈ Rd×H×W         such thatMaL [i, j, k] = aL[i].
      - This matrix is multiplied element wise with the output of the CNN MGA(xI,xL)=M(h(xL))⊙xI =M(aL)⊙xI
      -
      - Fusion through concatenation
      - If through concatenation Mconcat(xI,xL) = [vec(xI);vec(xL)]. Vec represents flattened inputs

-
  -
    - Policy Module-Learns policy to implement instructions

-
  -
    -
      - Output from the multimodal fusion unit(concatenation or GRU)-combined representation of visual element and instruction- is fed as input to policy module
      -
      - Through Imitation learning-from doom game

-
  - Contains fully-connected layer to estimate policy function
  - Oracle which tells exact actions to perform
  - Agent re-orients using left-right turns and moves forward while re-orienting again if the when the orientation angle is greater than min turn angle in env
  -
  - Through RL- Positive rewards and Negative rewards according to action
  - Uses A3C algorithm-uses deep NN to learn policy and value fn. Runs multiple threads to update parameters.A3C consists of LSTM layer followed by fully-connected layers
  - Uses Entropy Regularization- for improved exploration of env
  - Uses Generalized Advantage Estimator- to reduce policy learning gradient



**Environment**

-
  -
    - Create environment in which agent can execute NL instructions and gain positive rewards on successful completion of task.
    - Instruction is a combination of action+ attributes+ object
    - Instruction can have multiple attributes but actions and objects are limited to 1 per instruction
    - Attributes such as color shape size
    - 70 manually generated instructions and for each instruction env allows automatic creation of multiple episodes with randomly selected objects- one correct object and 4 other incorrect objects-(limited to 5 objects per episode) placed randomly in the episode
    - _Challenges_

-
  -
    -
      - same instruction can refer to different objects in different episodes. Ex &#39;Go to red card&#39;
      - Objects might occlude each other
      - Objects may not be present in the field of view of agent
      - Map can be complicated necessitating better exploration in order to make correct decision
    - _Difficulty levels in spawning of objects in episodes_
      - Easy-Objects at fixed locations along single line along field of view
      - Medium- Objects at random locations, but in field of view. Agent in fixed location
      - Hard- Objects and agent at random locations. Objects may or may not be in the field of view initially. Agent needs to explore map.



**Experimental Setup**

-
  -
    - Experiments are performed in all three difficulty modes
    - Objects restricted to 5 per setup(1 correct and 4 incorrect)
    - In training objects spawned from set of 55 instructions. Additional 15 are kept out for testing in zero-shot evaluation(never seen)
    - Episode ends when agent reaches any object or episode time=30 elapses
    - Evaluation metric is &#39;accuracy&#39;-reaching correct object before time elapses
    - _Two scenarios for evaluation_

-
  -
    -
      - _Multitask-generalization_
      - To make sure model isn&#39;t overfitting on training set and can perform with instructions on unseen maps
      - Unseen maps but training set instructions

-
  -
    -
      - _Zero-shot Evaluation_
      - To test whether model can generalize to new conditions(unseen both)
      - Both instructions and maps are unseen in this evaluation



**Hyperparameters**

-
  -
    - Input to NN= encoded instruction through GRU of size 256+3x300x168 RGB image
    - First layer Convolutional with 128 filters of kernel size and stride 4
    - Second layer convolutional with 64 filters of 4x4 kernel size and stride 2
    - Third layer convolutional with 64 filters of 4x4 kernel size with stride 2

-
  -
    - _Imitation learning approach_
      - Run experiments using both Behavioral cloning and DAgger
      - Data generation and policy update is done per every outer interaction
      - Policy learner for imitation contains fully-connected linear layer of size 512- connected to 3 neurons
      - In each data generation step state trajectories of oracle&#39;s policy from both BC and DAgger are sampled and mixed. Mixing governed by an exploration co-efficient with linear decay from 1 to 0. For each state optimal action is collected from policy oracle
      - This(policy updation) is done for 10 epochs over all state-action pairs learnt till now using RMSProp optimizer
      - BC and DAgger both use Huber loss between estimated policy and optimal policy(given by policy oracle)

- _Reinforcement Learning Approach_


  - With A3C algorithm
  - Policy learning module has
  - First linear layer of size 256
  - Second layer LSTM of size 256-to encode history of state observations
  - LSTM layer connected to single neuron to predict value functions
  - LSTM layer also connected to 3 other neurons to predict policy functions
  - All parameters are shared through network except for final fully-connected layer
  - All convolutional and linear layers have ReLu activations.
  - Model trained using Stochastic gradient descent
  - Learning rate:0.001
  - Discount factor 0.99 for calculating expected rewards
  - 16 parallel threads are run for each experiment
  - Meansquared loss used for loss between estimated value fn and discounted sum of rewards for training w.r.t value fn
  - Policy gradient loss used for training w.r.t policy function



**Conclusion**

- Models(A3C for RL and BC/DAgger for imitation) using GRU outperformed in both Multitask and Zero-Shot task generalization across all modes of difficulty
