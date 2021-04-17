# World Models

### Introduction

Have you wondered how you can walk around your home almost effortlessly with your eyes closed? How is a goal keeper able to jump in the direction of the football even before he's has time to process the visual input? Can you recall how your kindergarten classroom looked like?

All these are possible because we form mental models of the world around us. If you think about it, most of our world models are not very high resolution but are still useful. Based on these models we are able to preemptively predict events in our environment. These models help us build our reflexes over time. 

The authors of the paper *World Models* developed agents capable of developing world models. They also explore if a policy learnt using on the world model environment is transferable to a real-world environment.

### Model Components

The authors suggest a model inspired by the human cognitive system. The model has a visual sensory component, a memory component, and a decision making component. 

![World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled.png](World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled.png)

The visual component is responsible for compressing the visual input frames into small representative code. The memory component makes predictions about future visual observations (in terms of representative code) based on historical information. Finally, the decision making component decides what actions need to be performed by the agent based on representations of the visual and memory components.

**Visual component - V Model**

![World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%201.png](World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%201.png)

The agent receives a high-dimensional visual input from the environment. Now, the role of V is to learn a condensed representation of the visual input (frame) in such a way that there is minimal difference between the original frame and the frame produced from decoding the condensed representation. For this, the paper used a simple Variational Autoencoder(VAE). As a brief reminder, a VAE learns the latent space distribution of the input in order to produce new output which are similar to the input. In our case, the VAE helps to learn the latent vector *z* of each visual observation(frame).

**MDN-RNN - M Model**

![World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%202.png](World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%202.png)

The M model is responsible for predicting the future *z* values that model V is expected to produce. In order to take into account the temporal aspect of predicting the next *z*  and the stochastic nature of most RL environments, the authors use an RNN with a Mixture Density Network output layer. While RNN takes care of the temporal aspect, the MDN outputs a probability density p(*z*) over the next *z* values to be generated.

**Controller - C Model**

The V and M models are not aware of the rewards in the environment. Based on the representations from V and M, the controller chooses actions that maximize the expected cumulative reward from the environment. For this purpose a single layer linear model is used.

### The Agent - V,M, and C

![World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%203.png](World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%203.png)

Finally, the agent is all the V,M and C models put together like seen above. The flow is as follows. V first receives a raw visual observation at time $t$ from the environment that it converts into a condensed encoded representation $z_t$. This along with the hidden state $h_t$ (hidden states contain representations of previous inputs providing historical context)of M are passed as inputs to C. The controller chooses an action $a_t$ that the agent will perform in the environment. As a result the environment changes. Now, M will take the current $z_t$ and $a_t$ to update its hidden state to $h_{t+1}$ that will be used for $z_{t+1}$ and $a_{t+1}$.

The pseudo code for the flow is as follows

![World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%204.png](World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%204.png)

### Learning from a Dream

The M model of the agent allows for the agent to train based on its dreams. But what is a dream? To generate a dream, we make use of the probability distribution of next expected z **viz $*z_{t+1}*$and sample from that distribution. We are now not sampling from the real-world, we are sampling from the world model. Below is a flow I drew for myself to understand the flow better.

![World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%205.png](World%20Models%2023057b833efe446d98158b2cfaca298b/Untitled%205.png)

### My Thoughts

I find the world models to be a novel idea modeled after human cognitive approach. I am trying to think of applications for such a model though. The V model is definitely useful for reduce the learning space as it encodes raw input. However, the model is not anything novel. Regarding the MDN-RNN, logically, what occurs to me first is to say that it might be useful in applications which require spontaneous responses. However, computer processing speeds are way faster than human processing speeds for this mechanism to be useful in such applications. Moreover, training from a dream, like mentioned in the paper, can produce additional complications. Since we are sampling from the probability density we might sample things having less probabilities of occurring, leading to imagining and training on situations that might not part of the real-world environment.