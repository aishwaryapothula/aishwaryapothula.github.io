# HLAI Course Summary

**Intelligence**

Intelligence is defined as an agent's ability to achieve goals in a wide range of environments. While we have such agents in movies such as ExMachina and Transendence, what is stopping us from building such AI in the real-world?

Then, what is human level intelligence? 

> An agent has human level artificial intelligence if there exists a symbolic description for every feasible sensory input and agent action sequence, such that the agent can update the behavior policy equally whether it receives the symbolic description or it experiences the sensory input and the action sequence itself.

Let's say you have never seen snow. Human intelligence is the ability to form and update a perception of snow either by directly interacting with it or by hearing or reading that is is white and crumbly in nature. 

Consequently, though we have models that can communicate it natural language such as GPT3, we cannot say that they possess human intelligence. 

**Challenge**

There are two key factors that are important in building models capable of human level intelligence: **capability** and **environment**. A model fully capable of intelligent behavior will not be able to behave so if not exposed to the right environment. Conversely, a model which does not have the capabilities for intelligence will not learn to be intelligent even if exposed to the right environment. Take for example Mowgli, a human child brought up by animals. Though he has the capability for language, he cannot speak it because he has not been exposed to it. Similarly, a chimpanzee bought up humans cannot learn language beyond a point for the lack of capability on its part.

The issue with trying to provide a right environment for human level learning is that humans have a multitude of experiences. Trying to simulate all of them is impossible. On the other hand, deploying a robot to be brought up in human environments has its own share of problems in terms of reproducibility and expenses incurred to make frequent modifications to the model. The challenge is to find a sufficient experiences for development of human intelligence. 

**Ideas to build an Approach**

Taking inspiration from Turing's suggestion to simulate a child's mind instead of an adult's mind, we can make the problem of creating a sufficient environment  and capable model for human intelligence more tractable. 

The environment can be constructed in a way that it has open-ended tasks, humanoid body for the agent and supports longitudinal development. It is also important that the environment contains tests to evaluate the learning progress of the agent.

The model can be developed such that rewards for reinforcing behavior are generated internally when certain hard-coded aspects such as hunger and curiosity are met. The thinking of the learning model can be represented in vector form to represent all modalities.

**Take Away**

Current approaches border on the extremes by trying to  either replicate the human brain to develop artificial intelligence or build rule-based behaviors. Rather, it would help to focus on uncovering the principles behind human behavior. 

**My Thoughts**

While limiting ourselves to building a model of human infants and sufficient experiences for human infant level experiences abundantly reduces the complexity of the challenge, the experiences of infants are still vast to simulate. How can we evaluate sufficiency? For example, if an model is not passing evaluations of developmental progress, how much percentage of the failure should we ascertain to the capability of the model vs sufficiency of the environment?