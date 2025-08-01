# RL Algorithms

A collection of Reinforcement Learning algorithms implemented in PyTorch. This repository currently contains implementations of state-of-the-art RL algorithms for continuous control tasks.

##  Current Implementations

### Soft Actor-Critic (SAC)
- **Location**: `soft-actor-critic/`
- **Paper**: [Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor](https://arxiv.org/abs/1801.01290)
- **Environment**: Inverted Pendulum (PyBullet)

##  Project Structure

```
RL-algorithms/
├── soft-actor-critic/
│   ├── main.py          # Training script
│   ├── sac_torch.py     # SAC agent implementation
│   ├── networks.py      # Neural network architectures
│   ├── buffer.py        # Experience replay buffer
│   ├── utils.py         # Utility functions
│   └── plots/           # Training plots and results
├── README.md
└── .venv/              # Virtual environment
```

##  Requirements

- Python 3.7+
- PyTorch
- Gymnasium
- PyBullet
- NumPy
- Matplotlib

##  Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd RL-algorithms
   ```

3. **Install dependencies**
   ```bash
   pip install torch gymnasium pybullet-gymnasium numpy matplotlib
   ```

4. **Run SAC training**
   ```bash
   cd soft-actor-critic
   python main.py
   ```

##  Training

The SAC implementation trains on the Inverted Pendulum environment from PyBullet. The training process:

- Runs for 250 episodes by default
- Saves the best performing model automatically
- Generates learning curves in the `plots/` directory
- Supports checkpoint loading for continued training

### Key Features

- **Experience Replay Buffer**: Efficient memory management for off-policy learning
- **Twin Critics**: Reduces overestimation bias
- **Stochastic Policy**: Enables exploration through entropy maximization
- **Automatic Model Saving**: Preserves best performing models
- **Learning Curves**: Visualizes training progress

##  Configuration

You can modify training parameters in `main.py`:

- `n_games`: Number of training episodes
- `alpha`: Actor learning rate
- `beta`: Critic learning rate
- `gamma`: Discount factor
- `tau`: Soft update parameter
- `batch_size`: Training batch size

##  Results

Training results and learning curves are automatically saved in the `plots/` directory. The SAC algorithm typically achieves stable performance on the Inverted Pendulum task within 100-200 episodes.

