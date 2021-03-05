# Grounded Language Learning in 3D Simulated World

## **Introduction**

Think of the words fluffy, purple, salty, citrus fragrance, and loud. We quickly realize that each of these words is a personal perception rooted in combinations of human senses of touch, sight, taste, smell and hearing. Now, think of the words happy, intelligence, and love. These words are a bit more complicated and take time for us to truly understand as they cannot be directly perceived. An understanding of these abstract words emerges as we grow older gaining more experiences. In either case, it is clear that we associate natural language with our perceptions of the world.

In a world of ubiquitous technology that performs actions to execute human-related tasks, isn't it critical to be able to communicate with technology in human language ? Imaginably, it is a mammoth task given the range, complexity, depth and contextuality of language. 

> We are increasingly surrounded by artificially intelligent technology that takes decisions and executes actions on our behalf. This creates a pressing need for general means to communicate with, instruct and guide artificial agents, with human language the most compelling means for such communication

The paper presents an endeavor to teach natural language to artificial agents in a way that humans understand language, through perception. This approach is called grounded language learning.

## **Paper's Approach**

**Agent Input and Observations**

To achieve grounded language learning, an agent is facilitated with visual, text and reward input signals and is designed to perform a set of discrete actions. 

![Grounded%20Language%20Learning%20in%203D%20Simulated%20World%200415429a603940e39d677cc1ea5b514a/Untitled.png](Grounded%20Language%20Learning%20in%203D%20Simulated%20World%200415429a603940e39d677cc1ea5b514a/Untitled.png)

(L) Agent Observations (R) Agent Actions ; Source : [https://arxiv.org/pdf/1706.06551.pdf](https://arxiv.org/pdf/1706.06551.pdf)

**Environment**

The agent operates in an extended version of the DeepMind environment. Throughout, the agent is able to control its visual input by exploring the environment. 

![Grounded%20Language%20Learning%20in%203D%20Simulated%20World%200415429a603940e39d677cc1ea5b514a/Untitled%201.png](Grounded%20Language%20Learning%20in%203D%20Simulated%20World%200415429a603940e39d677cc1ea5b514a/Untitled%201.png)

Agent's view of the DeepMind 3D virtual environment ; Source : [https://arxiv.org/pdf/1706.06551.pdf](https://arxiv.org/pdf/1706.06551.pdf)

**Goal**

The goal is for the agent to correctly pickup specific objects in its environment based on textual instructions describing the object to be picked up. An example of the textual description the agent receives is "***pick the red object next to the green object***". 

"In the above example, the agent begins in position 1 and immediately receives the instruction to pick the red object next to the green object. It explores the two-room layout, viewing objects and their relative positions before retrieving the object that best conforms to the instruction. This exploration and selection behaviour emerges entirely from the reward-driven learning and is not preprogrammed. When training on a task such as this, there are billions of possible episodes that the agent can experience, containing different objects in different positions across different room layouts. " [source](https://arxiv.org/pdf/1706.06551.pdf)

**Model To Train Agent**

The author's have trained the model using a combination of Reinforcement learning and Unsupervised learning.  

![Grounded%20Language%20Learning%20in%203D%20Simulated%20World%200415429a603940e39d677cc1ea5b514a/Untitled%202.png](Grounded%20Language%20Learning%20in%203D%20Simulated%20World%200415429a603940e39d677cc1ea5b514a/Untitled%202.png)

Schematic representation of agent design where A is action module, M mixing module that mixes visual and text signals. RP is reward prediction and VR is Value replay

**Experiments**

The experiments conducted in the paper can be classified into the following categories

1. Test to evaluate the ability to acquire diverse vocabulary related to observable objects in the environment
2. Evaluation of the agent's ability to use the acquired lexical knowledge to interpret combinations of familiar and novel words
3. "Test for agent's ability to learn less concrete aspects of language, including relations concepts." [source](https://arxiv.org/pdf/1706.06551.pdf) Examples of relational words are *larger, smaller, lighter, darker* etc
4. Experiments were also conducted to test the agent's ability to understand instructions indicating behavior. Example of one such instruction is  "pick the X object or pick all X, where X denotes a color".

**Conclusion**

The agent is able to learn vocabulary pertinent to observable objects in the environment and later use this lexical knowledge to learn and execute new instructions. As a consequence, the speed of learning language increases as it learns more vocabulary. 

## My Thoughts

I agree that there is a need for machines to be designed to understand natural language in a way that humans relate to language. I like that the present approach eliminates some of the pain points of previous approaches such as the requirement for the syntax and semantics of language to be hard coded for the agent to learn. Being able to implement a type of learning in which the agent is able to learn new phrases quickly based on existing lexical knowledge is impressive. I specifically appreciate that the approach allows for learning through both rewards and interaction, just like humans learn. 

I believe that embodied learning is a great approach to grounded language learning as it is closest to how humans learn language - through perception. Consequently, I think the paper can be improved by experiments with more perceptual modalities input such as audio and touch. Moreover, the agent used is situated in a relatively narrow environment. With an understanding that an agent's learning is a function of the environment, a richer environment would lead to richer learning. Somewhat connected to this is the issue with the actions the agent is able to perform in the environment. The actions are pre-designed and are limited, interfering with the agent's ability to explore the environment. However, the author's might have introduced the constraint to make the learning easier.