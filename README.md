# Letter Dice Game

Welcome to the Letter Dice Game, an engaging and challenging word puzzle game inspired by the classic dice-based word game. This game is designed to be a self-contained, easy-to-set-up and play game that runs on Kubernetes.

## Overview

The Letter Dice Game generates a random board of letters by rolling dice with letters on each face. Players aim to find words in sequences of adjacent letters, where "adjacent" includes horizontal, vertical, and diagonal neighbors. It's a fun and educational way to enhance your vocabulary and spelling skills!

## Features

- **Self-contained Deployment**: Everything you need is bundled in a single YAML file. 
- **Automatic Board Generation**: The board is randomly generated every 10 seconds, offering a new challenge each time.
- **Customizable Gameplay**: You can modify the script to change the dice configuration, altering the gameplay experience.

## Prerequisites

- A Kubernetes cluster
- Kubectl installed and configured to interact with your cluster

## Installation

1. **Clone the Repository**: First, clone the repository to your local machine using:
   ```bash
   wget https://raw.githubusercontent.com/mlmerchant/letter-dice-game/main/letter-dice-game.yaml
   ```
2. **Deploy to Kubernetes**: Apply the YAML file to your cluster:
   ```bash
   kubectl apply -f letter-dice-game.yaml
   ```
3. **Access the Game**: Once deployed, the game is accessible via a NodePort service. You can view the board by navigating to `http://[your-cluster-ip]:30007`.

## Components

- **Nginx Container**: Serves the game board as a static image.
- **Ubuntu Container**: Runs a script to generate the game board.
- **Python Container**: Used as an init container to create letter tiles.
- **ConfigMaps**: Contains scripts and Nginx configuration.

## Customization

Feel free to modify the scripts in the ConfigMap to alter the gameplay. For example, you can change the dice configuration to include different letters or adjust the frequency of board updates.

## Contributing

We welcome contributions! If you have suggestions or improvements, please feel free to fork the repository and submit a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

Enjoy the game, and may it challenge and improve your word-finding skills! 🎲📚
