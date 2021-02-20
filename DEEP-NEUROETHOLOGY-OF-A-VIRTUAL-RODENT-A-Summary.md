# DEEP NEUROETHOLOGY OF A VIRTUAL RODENT - A Summary

[https://www.youtube.com/watch?v=XV3tz1bpjdg&feature=youtu.be](https://www.youtube.com/watch?v=XV3tz1bpjdg&feature=youtu.be)

---

**Introduction**

Animals possess a natural ability to perform a wide range of tasks. Their nervous system can adapt their behaviors to suit various goals and contexts. However, in the case of machines, we are yet to come across neural networks capable of this level of generality.  

> Recent efforts at the interface of neuroscience and machine learning have sparked renewed interest in constructive approaches in which artificial models that solve tasks similar to those solved by animals serve as normative models of biological intelligence. Researchers have attempted to leverage these models to gain insights into the functional transformations implemented by neurobiological circuits.

The paper uses a reverse engineering approach to identifying the underpinnings of neural control in the nervous system. The crux of the paper is to construct a virtual rodent that is able to solve tasks in an environment, in order to analyze and understand the types of representations and dynamics employed by the virtual neural system to coordinate complex movements in different contexts. The analysis is done using neuroscience methods. 

**Architecture of the Virtual Rodent**

![DEEP%20NEUROETHOLOGY%20OF%20A%20VIRTUAL%20RODENT%20-%20A%20Summary%205645f78ec44a457e9c8c1fe23a4c47d8/Untitled.png](DEEP%20NEUROETHOLOGY%20OF%20A%20VIRTUAL%20RODENT%20-%20A%20Summary%205645f78ec44a457e9c8c1fe23a4c47d8/Untitled.png)

The virtual rodent is an embodied model equipped with artificial nervous system (neural network), actuators that it can modify to perform motor activity, visual and proprioceptory sensory input data.  Body measurements are based on the measurements of lab rats. The virtual rodent neural network is trained using Actor Critic algorithm to solve a set of tasks in an environment by performing a variety of complex locomotor behaviors. 

![DEEP%20NEUROETHOLOGY%20OF%20A%20VIRTUAL%20RODENT%20-%20A%20Summary%205645f78ec44a457e9c8c1fe23a4c47d8/Untitled%201.png](DEEP%20NEUROETHOLOGY%20OF%20A%20VIRTUAL%20RODENT%20-%20A%20Summary%205645f78ec44a457e9c8c1fe23a4c47d8/Untitled%201.png)

**Tasks solved by the Virtual Rodent**

![DEEP%20NEUROETHOLOGY%20OF%20A%20VIRTUAL%20RODENT%20-%20A%20Summary%205645f78ec44a457e9c8c1fe23a4c47d8/Untitled%202.png](DEEP%20NEUROETHOLOGY%20OF%20A%20VIRTUAL%20RODENT%20-%20A%20Summary%205645f78ec44a457e9c8c1fe23a4c47d8/Untitled%202.png)

 The tasks described in the paper are

1. Running at a target velocity over gaps along a corridor. Reward is given when target velocity is achieved.
2. Foraging through a maze to gather collectables (blue orbs). Reward is given for acquiring each blue orb
3. Escaping a bowl shaped hilly terrain. Reward is proportional to the distance covered from the center of the terrain.
4. Activating orbs in an open field by tapping them twice within a tap interval of 800 ms. Sparse rewards are provided on the first and second tap.

**Analysis of Artificial Neural Network**

The virtual nervous system is analyzed to study the inner workings of neural control which were then compared with biological neural control descriptions. During this process many commonalities were identified.

*For example*, the virtual rodent stored representations similar to behavior and postures in its core and policy layers, suggesting that this kind of representation is useful in producing moment-to-moment production of motor activities. Similar model of storing behavior representations to produce moment-to-moment motor activities has been proposed in biological action selection and motor control. 

As another example, analysis of artificial neural network revealed that motor activity patterns that are frequently reused were organized in sequences. Examples of such sequences are the ones used for running, jumping etc. This result is consistent with research linking sequential neural activity to stereotyped motor and task-oriented behavior in rodents. 

**My thoughts**

Essentially the approach here is reverse engineering - modeling intelligent behavior by training artificial neural networks and in turn analyzing the inner representations of these networks to understand biological neural systems. 

The advantage in the constructive approach is that it allows for the full observation of the model inputs and the inner workings of the artificial neural network. 

However, when it comes to using this approach for human intelligence, there are a number of limitations. Give the multitude of intelligent behaviors humans can exhibit, it is extremely difficult to first design a wide array of discrete tasks. The complexity only increases with the consideration of language. Moreover, it is even more difficult to design an artificial neural network that can accomplish these tasks for us to in turn analyze the inner workings of it. It might lead to a vicious circle wherein understanding of intelligence is needed to design an intelligent model that we can use to understand intelligence. 

Then the question arises, if we are already able to replicate human behavior, is there a need to understand the underpinnings of the neural system that controls it ?