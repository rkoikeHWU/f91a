# f91a - Smart Building 
In this assignment, you will model a simplified smart building as an MDP and use value iteration to compute the optimal operating strategy.

Problem Description

A smart building has three possible energy states:

Low Energy (L) – The building is cold and uncomfortable, but energy usage is low.

Medium Energy (M) – The building is comfortable with moderate energy usage.

High Energy (H) – The building is very comfortable but consuming a lot of energy.

The building controller can choose one of two actions at each time step:

Eco Mode (E) – Save energy, less aggressive heating.
Boost Mode (B) – Increase comfort quickly, but use more energy.
The goal is to maximize long-term comfort while avoiding excessive energy consumption. Transitions and Rewards From Low Energy (L)

Eco (E):
Reward = +1
Next state = L with probability 1
Boost (B):
Reward = +3
50% chance → M
50% chance → L
From Medium Energy (M)

Eco (E):
Reward = +2
70% chance → M
30% chance → L
Boost (B):
Reward = +4
60% chance → H
40% chance → M
From High Energy (H)

Eco (E):
Reward = +1
80% chance → M
20% chance → H
Boost (B): • Immediate penalty = −8
Next state = H with probability 1
MDP Parameters Discount factor: γ = 0.9

Students are required to implement value iteration in Python for the smart energy management MDP using the provided state space, action set, rewards, transition probabilities, and discount factor.

Your program must start from an initial value function V₀ where all state values are set to zero, and then automatically compute and print V₁, V₂, and V₃. The output format must clearly show the values for the three states Low, Medium, and High at each iteration so that the progression of values can be verified against expected patterns. Next, your implementation must continue running value iteration until convergence and output the final optimal values V*. Finally, your program must automatically extract and print the optimal policy from the converged value function.
