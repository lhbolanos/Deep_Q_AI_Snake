# Deep_Q_AI_Snake

AI Snake Game

Description: This program uses a deep learning algorithm with PyTorch in order to train an AI agent to play the game of snake via Python.

Concepts:
- Reinforcement Learning
- Deep Q Learning
- Agent

Environemnt:
- Anaconda is used to manage the environment to support machine learning.

Deep Q Learning:
- This RL approach was chosen to help the agent predict the next action to be taken.
- Model is a feed forward neural net with some linear layers.
- 3 Layers: Input, Hidden, Output
- The input layer takes in an input space of size 11 (state).
  - [danger straight/right/left, direction left/right/down/up, food left/right/up/down]
- Output layer generates predicted next action
  - straight [1,0,0] / right [0,1,0] / left [0,0,1]
- Loss Function uses Bellman Equation.

  Changes:
  - Fixed issue of spinning agent.
    - 'get_action' method did not provide updated value for 'final_move' when condition for exploration was not met.
    - Agent will now exploit its learning knowledge correctly rather than exploring randomly and select action based on model's prediction.
  - Save highest scoring model from testing to be used in future testing.
   - Program will now overwrite the contents of 'model.pth' only if the selected model performed better than it's previous iteration.
