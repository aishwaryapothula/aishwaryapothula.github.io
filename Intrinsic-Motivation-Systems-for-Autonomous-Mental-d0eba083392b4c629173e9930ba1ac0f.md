# Intrinsic Motivation Systems for Autonomous Mental Development

> Anyone who has ever played with an infant in its first year knows, for example, that it is extremely difficult to get the child to play with a toy that is chosen by the adult if other toys and objects are around.

### **Introduction**

Have you ever wondered what the motivations behind infant's actions are? Are they just random actions or are motivated by an adult's appreciation, hunger, curiosity, novelty? Or just done for the sake of it? 

The truth is, the actions are motivated by all of these, both intrinsic and extrinsic, in different ratios. Infants, especially, seem to be more motivated by intrinsic rewards such as curiosity, hunger than extrinsic rewards such as appreciation. 

This paper attempts to model intrinsic motivation through a framework called *Intelligent Adaptive Curiosity*(IAC). The framework is based on a the following observations about infant motivations and behavior. 

- Development is progressive and incremental. The complexity of activities undertaken are always progressive and the activities match the current capabilities of the infant. Development follows curriculums as proximodistal and cephalocaudal.
- Basic forms of motivation such as hunger etc cannot account for infants' exploratory behavior. Infants perform exploratory actions just for the sake of it, which by themselves are rewarding.
- It is observed that the most rewarding situations for an infant are those with intermediate level of novelty. Situations that lie between 'already familiar' and 'completely new'

### **Intelligent Adaptive Curiosity**

The framework models a kind of intrinsic motivation concerned with maximizing the **learning progress** of the agent. Trying to maximize learning can lead to exploring novel situations - the reason the framework is called curiosity. Similarly, once the novel situation is explored and mastered, it is no longer novel. This is the reason it is adaptive. Is it intelligent because it is modeled to keep the agent away from situations that are too familiar or too novel.

**Regions**

The framework works by first storing all sensory motor experiences as vector exemplars. It uses a mechanism by which this sensory motor space is incrementally split into regions. The regions are split so that the sum of variances of the sensory information weighed by the number of instances of them is minimal. Also, the paper sets the maximum number of exemplars in a region to be 250, to make the computation process efficient. A friendf mine, gave me a good analogy to understand this process. Let me share it with you. Imagine a piece-wise linear function - the function behave differently for different ranges of the input variable. By splitting the sensory-motor space, we are trying to identify ranges of sensory information for which a function behaves in a certain way. 

**Experts**

Once the regions are split, a separate *expert* is assigned to each region to learn the function applicable to it and predict future sensory motor experiences related to that region. Experts can be either neural networks or SVMs or memory-based methods.

**Learning process evaluation**

Now, the learning progress is also evaluated regionally. Each time the agent performs an action in a sensory-motor context, the expert associated with that region predicts the next sensory state. This predicted state is compared with the actual succeeding sensory state and the discrepancy error is noted. A list of these errors over time steps is maintained. The difference in mean error rate of 15 time steps is compared with the error rate of past 25 time steps. A decrease of this measure is considered as the learning progress.

**Action Selection**

This learning progress can be formulated as a reward and can be used as basis for action selection to maximize it.

### My Thoughts

The framework was applied on a couple of scenarios in which it shows promise by exhibiting the observed human behaviors mentioned in the introduction. The major limitation seems not to be the model but designing environments that promote more complex behavior.