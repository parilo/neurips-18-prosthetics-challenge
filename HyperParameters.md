# Hyperparameters used

## Fully Connected Agent

### Input parameters

| Parameter | Value |
| - | - |
| State Size | 344 |
| History Len | 1 |
| Action Size | 19 |
| Gamma | 0.99 |

### Actor network

| Parameter | Value |
| - | - |
| Layers | 512, 512, 256, 256 |
| Layer options | Layer Normalization, No biases (except last layer) |
| Activation | ReLU |
| Output Activation | Tanh |

## LAMA agent

### Input parameters

| Parameter | Value |
| - | - |
| State Size | 344 |
| History Len | 4 |
| Action Size | 19 |
| Gamma | 0.99 |

### Actor network

| Parameter | Value |
| - | - |
| Layers | 512, 512, 256, 1024 (LAMA) |
| Layer options | Layer Normalization, No biases (except last layer) |
| Activation | ReLU |
| Output Activation | Tanh |

## Common hyperparameters

### Critic network

| Parameter | Value |
| - | - |
| Layers | 512, 512, 256, 256 (atoms) |
| Layer options | Layer Normalization, No biases (except last layer) |
| Activation | ReLU |

### Exploration parameters

| Parameter | Value |
| - | - |
| Action Noise Probability | 0.7 |
| Parameter Noise Probability | 0.2 |
| Max Action Noise | 0.2 |
| Max Parameter Noise | 0.2 |

### Reward shaping

| Parameter | Value |
| - | - |
| Reward Scale: | 0.1 |
| Crossing Legs Penalty | 10. |
| Max Reward (subtract 8 from original reward) | 2.0 |

### Algorithm

| Parameter | Value |
| - | - |
| Number of critics | 2 |
| TD3: Action Noise Std | 0.15 |
| TD3: Action Noise Clip | 0.5 |
| Clip Min Action, Max Action | -1.0, 1.0 |
| Soft Target Update Tau Actor | 0.0025 |
| Soft Target Update Tau Critic | 0.005 |

### Optimizer

| Parameter | Value |
| - | - |
| Actor Optimizer | Adam, learning rate 1e-3 |
| Critic Optimizer | Adam, learning rate 1e-3 |
| Actor Gradient Clipping | 1.0 |
| Scheduling Optimizer Params | 0.5 * LR at 1.5M, 0.25 * LR at 3M |
| Loss | HuberLoss, Clip Delta 1.0 |
| Batch Size | 256 |
| Replay Buffer Size | 5M |
| Start Learning At | 15K samples in replay buffer |
