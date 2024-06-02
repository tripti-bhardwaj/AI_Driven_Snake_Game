# AI_Driven_Snake_Game

This project is an AI-driven version of the classic Snake game, utilizing deep reinforcement learning with a neural network to train the snake to play the game. The AI agent uses a Q-learning algorithm with experience replay to improve its performance over time.

## Features

- **Deep Q-Learning:** Uses a neural network to approximate the Q-value function.
- **Experience Replay:** Stores past experiences to break the correlation between consecutive learning steps.
- **PyTorch Implementation:** Leverages the PyTorch library for building and training the neural network.
- **Real-time Training Visualization:** Displays the training progress using matplotlib.

## Requirements

- Python 3.6+
- Pygame
- PyTorch
- Matplotlib
- Numpy

## Installation

1. **Clone the repository:**

```bash
git clone https://github.com/your-username/snake-ai.git
cd snake-ai
```

2. **Install the required packages:**

```bash
pip install -r requirements.txt
```

## Files Overview

- `agent.py`: Contains the `Agent` class that defines the reinforcement learning agent.
- `ai.py`: Contains the game logic for the Snake game including the environment definition.
- `helper.py`: Contains utility functions for plotting the training progress.
- `model.py`: Defines the neural network model and the Q-learning trainer.
- `snakegame.py`: A human-playable version of the Snake game for reference and testing.

## How to Run

1. **Train the AI Agent:**

   To start training the AI agent, simply run the `agent.py` script:

   ```bash
   python agent.py
   ```

   The training process will start, and you will see a live plot of the scores and mean scores over the games.

2. **Play the Game Manually:**

   If you want to play the game manually, you can run the `snakegame.py` script:

   ```bash
   python snakegame.py
   ```

   Use the arrow keys to control the snake and try to eat the food to grow in size.

## Code Structure

### agent.py

This file contains the `Agent` class which is responsible for:

- Interacting with the game environment to get the current state.
- Deciding on the next action to take based on the current state.
- Training the neural network with experience replay.
- Managing memory of past experiences.

### ai.py

This file contains the `SnakeGameAI` class which defines the game environment and the rules of the Snake game. It includes methods for:

- Resetting the game state.
- Placing food at random positions.
- Updating the game state based on the agent's actions.
- Checking for collisions.

### helper.py

This file contains utility functions for plotting the training progress using matplotlib. The `plot` function updates the plot with the current scores and mean scores.

### model.py

This file defines the neural network architecture using PyTorch and the Q-learning trainer. The `Linear_QNet` class defines a simple feedforward neural network with one hidden layer. The `QTrainer` class handles the training process using the Adam optimizer and mean squared error loss.

### snakegame.py

This file contains the `SnakeGame` class which allows you to play the Snake game manually using the arrow keys. It is similar to `ai.py` but is designed for human interaction.

## Training Details

- **State Representation:** The state is represented by an 11-dimensional vector including information about the current direction of the snake, the location of the food relative to the snake, and whether there is a danger straight ahead, to the right, or to the left.
- **Action Space:** The action space consists of three actions: move straight, turn right, and turn left.
- **Reward System:** The agent receives a reward of +10 for eating food, -10 for dying (colliding with walls or itself), and 0 otherwise.
- **Neural Network:** The neural network has an input layer of size 11, one hidden layer of size 256, and an output layer of size 3.

## Future Improvements

- Add more complex state representations to improve the AI's performance.
- Experiment with different neural network architectures and hyperparameters.
- Implement other reinforcement learning algorithms like Dueling DQN, Double DQN, etc.
- Add more features to the game, such as obstacles and different levels.

Feel free to contribute to this project by opening issues or submitting pull requests. For any questions or suggestions, please contact [your-email@example.com](mailto:your-email@example.com).
