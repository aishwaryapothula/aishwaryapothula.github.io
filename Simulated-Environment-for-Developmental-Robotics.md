# Simulated Environment for Developmental Robotics - A review

**Introduction**

We currently have AI that can hold conversations, beat us at games such as chess and Go, drive, collaborate etc. While remarkable progress has been made building goal oriented models, the paper asks the question, "why isn't there an AI that can do it all"?, like us humans can. After all, intelligence is defined as the "ability to achieve goals in a wide range of environments".

The paper explores the reasons to why such an AI is not developed and, as a solution, proposes an environment which can potentially aid the development of such an algorithm. 

**Limitations in previous research for building general AI**

The paper claims the following reasons to be the limiting factors in developing a learning algorithm that achieve human-level intelligence.

1. Past researches have focused on developing task-oriented models, resulting in models that cannot be generalized to diverse tasks. 
2. Refined and focussed datasets were used for training instead of broad and noisy datasets which are more similar to the experiences humans encounter
3. The models were trained on explicit rewards. Human motivation for learning is generally internal. Ex: Curiosity, hunger.
4. The focus has been on trying to find necessary mechanisms or components of human intelligence rather than finding sufficient conditions.

**Proposed Environment**

The authors try to address these limitations of past research by taking inspiration from the development of a child. A human child is born with negligible skills and means of survival. However, in a short span of time, after being exposed to diverse experiences, a human child is capable of performing tasks in multiple domains. The paper proposes a simulated environment(SEDRO) that can provide diverse open-ended experiences for an artificial agent ranging from those of a human fetus to a 12 month old. 

![Simulated%20Environment%20for%20Developmental%20Robotics%20-%20dad58b004daf431996f3752d999754c8/Untitled.png](Simulated%20Environment%20for%20Developmental%20Robotics%20-%20dad58b004daf431996f3752d999754c8/Untitled.png)

Screenshots the proposed environment. (L) represents the agent in a fetus environment. (R) depicts the caretaker interacting with the agent in the crib.

The main components of SEDRo are the learning agent and the simulated environment. SEDRo also contains the body of the agent, a caregiver character, interactable objects such as toys, cribs, walls etc. It implements embodied cognition by designing the learning agent to interact with its environment using its body. The agent achieves this by controlling its muscles according to sensory signals. Sensory input consists of touch, vision, acceleration, interoception, and proprioception. To replicate human sensorimotor development, the agent's sensory inputs are scaffolded according to a curriculum. The agent's ability to interact with its surroundings is gradually enabled as it reaches developmental milestones(refer table below), evaluated through experiments inspired from developmental psychology. For example, initially, the agent is nearsighted for the first few weeks similar to human infants. Then, as the agent learns to gain control of its eye movement, perceptual accuracy is increased. The role of the caregiver is to provide cognitive bootstrapping and social learning to the agent. For instance, the caregiver talks to the baby agent or shows the agent how to interact with the toys etc. The overall goal of the learning model/agent is to compose an appropriate output behavior given a sensory input.

![Simulated%20Environment%20for%20Developmental%20Robotics%20-%20dad58b004daf431996f3752d999754c8/Untitled%201.png](Simulated%20Environment%20for%20Developmental%20Robotics%20-%20dad58b004daf431996f3752d999754c8/Untitled%201.png)

**My Thoughts**

One of the main merits of this work is its proposal of using experiments from the field of developmental psychology to evaluate developmental progress in artificial agents. Since the agent capabilities are built to reflect child development, it makes sense to use experiments designed to evaluate human development for tracking agent development. This is an under-explored approach which can yield interesting insights allowing us to draw parallels. Moreover, it overcomes the problems identified with past approaches by 1) targeting a variety of skills, 2) simulating real-world infant experiences, 3) designing the agent to be internal rather than dependent on external rewards, 4)focussing on trying to find sufficient conditions for developing human-level intelligence.

The limitations to the paper can be framed into two questions. In terms of providing diverse open-ended experiences through the environment, how can the researchers provide experiences as diverse as a human toddler's? Even if the aim is not to simulate all real-world experiences, how do they know what is a sufficient environment that can support the development of human-level intelligence? More specifically, if an agent fails an evaluation, what percentage of the failure can be attributed to the learning algorithm and what percept to the quality and quantity of experiences in the environment?