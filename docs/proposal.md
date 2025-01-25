---
layout: default
title: Proposal
---

# Summary of the Project
Our project focuses on **Sichuan Mahjong**, a fascinating game with unique mechanics.  
If the following explanation is not clear enough, here is a [video](https://www.youtube.com/watch?v=bj5LEAXcNwg) to help you better understand the game.

### Game Basics

The game consists of **108 cards** in total, categorized into three suits: **Wan, Tong, and Tiao.** Each suit contains numbers **1 to 9**, with **four copies of each card.**  
For example, there are four **1 Wan**, four **4 Tong**, and four **9 Tiao** cards.

At the start of the game, four players take turns. Three players receive **13 cards each**, while the **dealer (or "master")** receives **14 cards.** The dealer is always player **number 1.**  
This setup leaves **55 cards** remaining in the deck.

### Objective and Winning Conditions

To win, players must form a **winning combination** using the cards in their hand. A standard winning hand consists of:

- **Four sets of three cards (34 cards total):**  
  - A set can either be a sequence (e.g., 1-2-3) or a triplet (e.g., 6-6-6).
  - Each set must belong to the same suit.

- **One pair (2 cards):**  
  - The pair must have the same suit and number, such as 7-7.

When a player is **one card away** from forming a set, they can obtain the needed card in two ways:

1. **Drawing it from the deck.**  
2. **Claiming it from an opponent's discarded card.**

The method of obtaining the winning card affects the game's outcome:

- If a player wins by drawing the card themselves, the remaining players without a winning hand must pay the winner.
- If a player wins using a discarded card, the player who discarded it bears the cost of the winning combination.

### Gameplay Flow

1. The dealer (player 1) discards the first card.
2. The remaining players each draw a new card and discard one in turn.
3. This cycle continues until either there are no more cards in the deck or three players have completed their winning hands.

### Special Moves

A key feature of the game is **Peng (碰).**  
If a player has two identical cards and an opponent discards the same card, they can claim it to complete a triplet (three of a kind).  
After doing so, the player must discard another card from their hand, and the game proceeds to the next player.

For example, if player 1 discards a card and player 3 claims it for a **Peng**, the turn then moves to player 4.

### AI Development Goals

Our AI aims to maximize its **win rate**, which consists of two primary objectives:

1. **Winning as quickly as possible.**
2. **Forming high-value winning combinations.**

These two goals are often conflicting:

- Pursuing a quick win may result in a less valuable hand.
- Waiting for a higher-value combination increases the risk of losing opportunities.

To balance these objectives, the AI must develop both **calculation** and **reasoning** skills:

#### Calculation

- Since the total number of cards is fixed, the AI can track which cards have been discarded and are no longer available.

#### Reasoning

- Since the AI cannot see opponents' hands, it must infer their possible holdings based on their discards.
- For example, if a player discards a 9, it may indicate they already have a 7-8-9 sequence and no longer need the extra 9.

Through continuous simulations and learning, the AI will improve its performance using **Reinforcement Learning (RL)** techniques.  
Over time, it will become better at predicting opponents' strategies and making optimal decisions to increase its win rate.

# AI/ML Algorithms
We will likely use an off-policy DQN reinforcement learning method to train our Mahjong AI to optimize hand discards based on opponent behavior and what tiles are known to us (our hand + the discard pile).


# Evaluation Plan
To evaluate the success of our Sichuan Mahjong AI, we will focus on a combination of quantitative and qualitative metrics. Quantitative evaluation will include metrics such as the AI’s win rate, the average value of its winning combinations, the convergence of its reinforcement learning process, and its time efficiency. Specifically, we will measure the AI’s win rate over a large number of simulated games and compare it to random baseline players and rule-based players. Additionally, we will assess the average value of its winning combinations, ensuring the AI strikes a balance between forming quick wins and achieving high-value combinations. We will also track its learning process by monitoring cumulative rewards and other convergence metrics, while ensuring its decision-making remains computationally efficient during gameplay.
For qualitative evaluation, we will focus on analyzing the AI’s strategic decisions and its ability to adapt during gameplay. We will observe whether the AI avoids making plays that could benefit opponents, effectively balances between forming quick and high-value combinations, and learns to adapt to opponents’ strategies by analyzing their discarded cards. Failure cases will be examined to identify patterns in the AI’s weaknesses, such as over-prioritizing risky strategies or misjudging opponents’ hands. Additionally, we will simulate specific scenarios to verify that the AI correctly applies critical rules, such as deciding when to “peng” or discard a card. As a moonshot goal, we will test the AI against advanced players or in competitive scenarios to evaluate its ability to employ complex strategies, such as bluffing or misleading opponents through its card discards.
To visually represent the evaluation, we will use graphs and charts that illustrate the AI’s win rate improvement and average combination values over time. Comparative analysis against baseline players will be presented through bar charts or similar visualizations. Heatmaps will be used to explain the AI’s decision-making process, such as its reasoning for selecting or discarding specific cards based on the game state. These visualizations will provide an intuitive understanding of the AI’s strategic development and performance.
The evaluation will be conducted on simulated Sichuan Mahjong games adhering to standard rules. The AI is expected to achieve at least a 20% higher win rate than random players and a 10% higher average combination value than rule-based players. These expectations will demonstrate the AI’s ability to balance between winning quickly and forming valuable combinations. By combining both quantitative and qualitative evaluation approaches, we aim to ensure a robust assessment of the AI’s performance and identify potential areas for further improvement.
