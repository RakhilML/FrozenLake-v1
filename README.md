# FrozenLake-v1
The goal of the agent is to navigate from the start tile to the goal tile in the Frozen Lake environment using Q-learning and SARSA

# Scenario Overview
FrozenLake is a simple grid-world environment in which the agent (player) navigates
on a frozen lake surface to reach a goal tile while avoiding falling into holes. The
environment is represented as a grid, where each tile can be either frozen (F), a hole
(H), or the goal (G). The agent can take four possible actions: move up, down, left, or
right.

# Problem definition
The FrozenLake environment challenges an agent to navigate a treacherous frozen lake
from the Start (S) to the Goal (G) without tumbling into any treacherous Holes (H) by
traversing the slippery surface of the Frozen (F) lake. Due to the icy conditions, the agent
may not always move as intended, adding an element of uncertainty to its journey.

![image](https://github.com/RakhilML/FrozenLake-v1/assets/106943173/044948ed-74e8-4117-a4a2-f2280b149898)

# Random exploration

Random exploration would involve the agent randomly selecting actions to navigate the icy
terrain without any prior knowledge or planning. Here's how random exploration might work
in the Frozen Lake environment:

* Initialization: The agent starts at the designated starting point (S) on the frozen lake grid.
Random Action Selection: At each time step, the agent randomly selects one of the four
available actions (LEFT, DOWN, RIGHT, UP) with equal probability.
* Movement: The agent moves in the selected direction, but due to the slippery nature of the ice,
there is a chance that it may not move as intended. If the agent encounters a hole (H), it falls into
the hole and fails. If it reaches the goal (G), it succeeds.
* Exploration: Through random exploration, the agent explores various paths on the frozen
lake grid, including safe paths, holes, and the goal. This exploration helps the agent gain an
understanding of the environment's layout and the consequences of different actions.
* Learning: While random exploration does not involve learning from past experiences, it helps
initialize the agent's understanding of the environment and provides a baseline for comparison
with more sophisticated exploration strategies.
* Evaluation: After a certain number of episodes or time steps, the agent's performance can be
evaluated based on the number of successful reaches to the goal and the number of falls into
holes.

# Q-LEARNING (frozenlake.ipynb)
The code implements a Q-learning algorithm, which balances
exploration and exploitation. During training, the agent explores the environment by either
selecting the action with the highest Q-value (exploitation) or taking a random action
(exploration). This exploration strategy helps the agent discovers optimal policies.
*Algorithm Selection: The Q-learning algorithm is chosen for its simplicity and effectiveness
in tabular RL settings. Q-learning is a model-free, off-policy RL algorithm that learns the optimal
action-value function (Q-function) iteratively by updating Q-values based on observed
transitions and rewards. In this code, the Q-table is updated using the Bellman equation to
approximate the optimal Q-values.

# Results (Q-TABLE)

![image](https://github.com/RakhilML/FrozenLake-v1/assets/106943173/16cd43ac-cb52-4758-ad78-1eb302ae0e56)

# Results (Step-by-step)

![image](https://github.com/RakhilML/FrozenLake-v1/assets/106943173/2f9354fa-f399-4658-9645-aad7fa5d58e1)

# SARSA (frozenlake_sarsa.ipynb)
The SARSA algorithm is applied to the Frozen Lake environment, where an agent aims to
navigate a grid world from the starting state (S) to the goal state (G) while avoiding holes (H) on
the slippery ice surface (F). The agent can take four possible actions: move left, down, right, or
up
![image](https://github.com/RakhilML/FrozenLake-v1/assets/106943173/f78a4ac4-575f-4f04-9cdb-5cb0f7c6565f)

* Initialization: The SARSA agent initializes its Q-table with zeros to represent the action-values
for each state-action pair.
* Exploration: During training, the agent explores the environment using an epsilon-greedy
exploration strategy. It selects actions based on the current state and the epsilon parameter,
which controls the balance between exploration and exploitation.
* Action Execution and Learning: The agent interacts with the environment, selecting
actions and receiving rewards. After taking each action, it updates its Q-values using the SARSAupdate rule, which considers the immediate reward and the Q-value of the next state-action
pair.
* Training Loop: The training loop repeats for a fixed number of episodes, allowing the agent to
learn from its interactions with the environment and improve its policy over time.

# Results (Q-TABLE)
![image](https://github.com/RakhilML/FrozenLake-v1/assets/106943173/ce3e64e5-e900-4d67-9572-9f4f1e6ebb33)
# Results (Reward per episode)
![image](https://github.com/RakhilML/FrozenLake-v1/assets/106943173/a54d1f4f-c8c2-43ac-9b26-09db3b3d9468)

# Convergence-speed
* Q-learning: Q-learning tends to converge faster to an optimal policy, especially with a decaying
exploration rate, which can lead to quicker learning in simpler environments.
* SARSA: SARSA's smoother learning dynamics and conservative exploration may result in
slower but more stable convergence, potentially offering a more reliable performance in
complex or uncertain environments.

# DEMO-VIDEO
(https://youtu.be/5AhnIYvkztw)
