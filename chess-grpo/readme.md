♟️ Chess-GRPO: Reinforcement Learning via Verifiable Rewards

This project implements a Chess AI trained using Group Relative Policy Optimization (GRPO). The agent leverages Stockfish as a "Verifiable Reward" provider, bridging the gap between deep neural networks and classical chess engine heuristics.
🚀 Key Features

    GRPO Architecture: Implements group-based advantage estimation to optimize the policy without a separate value (critic) network, reducing memory overhead and complexity.

    RLVR (Reinforcement Learning from Verifiable Rewards): Uses Stockfish as a verifiable oracle to provide real-time advantage scores for sampled move groups.

    Two-Stage Training Pipeline:

        Supervised Pre-training: The model learns expert "instincts" by mimicking Stockfish Principal Variation (PV) moves across thousands of random positions.

        GRPO Refinement: The model explores move variations and is rewarded based on their relative strength compared to the group average.

    Advanced Sampling: Supports Temperature scaling and Top-p (Nucleus) sampling to balance creativity and strategic soundness during inference.

    Interactive UI: A custom notebook interface featuring ipywidgets for move input and chess.svg for real-time board rendering.

🛠️ Tech Stack

    PyTorch: Neural network architecture and GRPO optimization.

    python-chess: Move validation, board state logic, and SVG rendering.

    Stockfish: The verifiable reward engine for RL training.

    NumPy: Efficient board-to-tensor state representation.

    ipywidgets: Interactive UI components for the play environment.

🔧 Installation & Quick Start

    Install Dependencies:
    Bash

    pip install python-chess torch numpy

    Install Stockfish:
    Ensure the Stockfish binary is installed and correctly pointed to in the configuration (/usr/games/stockfish by default).

    Training:
    Run the training pipeline to perform Supervised Learning followed by GRPO refinement.

    Play:
    Execute the play_final(model) function to challenge the AI using UCI move notation (e.g., e2e4).

📝 Roadmap

    [ ] Implement Monte Carlo Tree Search (MCTS) for lookahead during play.

    [ ] Transition to bitboard state representations for faster training.

    [ ] Integrate a larger dataset of Grandmaster PGNs for initial pre-training.

Developed as an exploration into RLVR and Group Relative Policy Optimization.
