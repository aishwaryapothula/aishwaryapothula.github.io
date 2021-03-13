# How to Grow A Robot-Chapters 11&12

**Introduction**

The general theme of the book is to introduce an approach to build human-level AI that is also relatable to humans.  The first part of the book talks about the nature of the problem of building human level AI. The proposed approach and its implementation and results are discussed in the second part. The book finishes off by commenting on future trends in AI development.

The most important take away regarding the approach  that a an artificial agent would need to have a concept of self and behave in socially accepted ways to be relatable to us. The agent needs to perceive the environment in ways similar to us. To implement this, we cannot simply design a program; the agent needs to grow  in the environment and and autonomously explore to develop its subjective perception of the environment. 

Chapters 11 & 12 explore alternative approaches to developing such AI such as cybernetics, developmental robotics to finally come up with an architecture to develop a model. 

The question might arise," why are we pursuing Human-level AI?". The answer to the question is four part

1. Human level intelligence is considered the epitome of intelligence
2. Effective techniques of human cognition maybe be discovered in the process
3. There is general interest to see if the brain is just a machine that can be simulated
4. To see if Artificial Human Intelligence is a way to achieve AGI

Even thought achieving AGI may turn out out be impossible, the chance to discover human cognitive processes in the process is the motivation to pursue the approah.

**Approach**

Initial AI approaches saw intelligence as just the processing of high level symbols. However, questions started arising about the meaning of symbols and how AI can related symbols to the external events in the environment. A solution came along in the notion that some symbols have meaning in sensorimotor experience. and that higher level symbols can be represented using these elementary symbols. A gradual acceptance led to a major shift in AI philosophy. What this meant for robotics is the increased importance to not just the processing capabilities but also to the sensing capabilities. 

![How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled.png](How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled.png)

This shift in philosophy lead to a need for AI that is Situated, Embedded and Embodied.

![How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled%201.png](How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled%201.png)

**A new paradigm**

A new paradigm and a more general term called **enaction** was introduced, having the characteristics of 

1. Autonomy - self control
2. Embodiment - being influenced by the body
3. Emergence - behavior emerging from internal and external interactions
4. Experience - state of the system after its history of experiences
5. Sense Making - ability to learn regularities and contingencies in interactions

Based on the paradigm of enaction, a field called Developmental Robotics emerged, inspired by development of infant cognition. It is an interdisciplinary field also involving computer science and developmental psychology concerned with building models of human intelligence. The main areas of study are sensorimotor skills, visual development, social interactions and language. Most importantly, developmental robotics supports the importance of ontogeny (growing in the environment).

 

**Architecture**

The three questions that need to be explored when building an architecture based on developmental robotics are 

![How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled%202.png](How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled%202.png)

To consider the first question, the best approach would be to start at a level as low as possible. Choosing an intermediate level of model only increases the complexity in justifying what the model already knows. A reasonably good level would be the level of a newborn infant.

Regarding the trajectory of growth, developmental milestones and constraints are decided based on the embodiment body's biological similarity to a human infant. Constraints are limitations of many kinds, usually manifested in acuity of senses, richness of environment etc. An example of a constraint in infants would be the constraint on torso movement till eye and head movement have been mastered. Cephalocaudal and proximodistal development in human infants are good references for the developmental trajectory and constraints. Constraints help in reducing the complexity of task space and aid in development of cognition.

Following the enaction paradigm, given that we cannot set rewards for motivation (that would mean we are designing the thinking of the agent), how are we to incorporate motivation in an agent? The motivation needs to be internal to the agent. One approach is to model instrinsic motivation as a function of novelty ie the agent's attention is diverted to objects/events that the agent find novel. 

An model architecture designing by the author based on the exploration of the questions above results in the following

![How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled%203.png](How%20to%20Grow%20A%20Robot-Chapters%2011&12%205e47d5a980044196b6c44f4d97784192/Untitled%203.png)

**My thoughts**

I think theoretically, the approach is great as it eliminates many of the difficulties of task based AI. It will be able to generalize to any new scenarios or environments. The Ai developed under this approach would be easy to communicate with and relate to.

However, I am concerned about the pace of learning. How long can we wait before a system acclimatizes to a new environment and how will the threshold metrics be decided ? How much of robot learning can we relate to human learning processes? Also how much error can we allow in a system? How can we make sure that the perception and interpretations made by the system are ethical?

Moreover, when there are exceptional task based robots tailored to perform tasks, what will be the acceptance of these general agents be? Industry looks to standardize processes. The subjectivity in perception of the environment, while being one of the hallmarks of general intelligence, can become a bane. 

These are some questions that I would like to explore.