---
layout: default
title: Proposal
---

# Summary of the Project
Our project is based on Sichuan Mahjong, a really interesting game. In case the explanation is not enough, here is a video to help you understand. 

First of all, there are 108 cards in total. The cards are categorized in 3 kinds: wan, tong, tiao. Each of the wan, tong, tiao has numbers 1 - 9, and each of the cards has 4 in total. For example, there are four 1wan, four 4tong, and four 9 tiao. 

Then the game starts, there are four players in order in this game, like number 1, number 2, number 3 and number 4. Three players get 13 cards as start-up and one player gets 14 cards, who is called master. Master is always the player number 1. In this situation, there are 55 cards remaining in the shoe. 

In order to win, players should form a winning combination using the card in their hand, which is 3*4 + 1*2. 
3*4 is four sets of 3 cards. The 3-card combination can be a straight, like 1, 2, 3. Or it can be the same, like 6, 6, 6. Remember, each 3 card combination must be the same kind. 
1*2 is 1 set of 2 cards. The 2-card combination must be the same kind and same number, like 7, 7
In the condition that any player is only one card away from the winning combination, there are two ways to get the card.
Get it by yourself.
Get it from others’ throw-out card
For the winning combinations, there are different values for those. Once a player has the winning combination, if the player wins by getting by themself, the rest who don’t have winning combination will pay for the value. If the player wins by getting from others’ throw-out cards, The one who throws out the card will pay for the winning combination.

In the first round, the master will throw out a card. The rest of the players will get a new card and throw out a card. And in the rest rounds, people will get a new card and throw out a card. 

Here is the key point of this game. When one has two of the same kind and same cards, and someone throws out this card, they can do an operation: peng. It means that you make a 3-card combination with your two cards and the one others throw out. At this point, since you get a new card, you need to throw out one card. And the game continues by the next player. For example, number 1 throws out a card and number 3 gets this card, the next player who gets a card is number 4.

The game will not end until no more cards in the shoe or three players have the winning combination.
These are the basic rules of this game, just in case you want to know.  Our AI is trying to learn to make his win rate as high as possible. The win rate has two aspects.
1. It will try to be the first one who has the winning combination.
2. It will try to form the better winning combination. 

Actually these two are in conflict and the AI will try the best to reach the balance. For the first aspect, if the player wants to win as fast as possible, then the winning combination will not be that valuable. However, if the player wants to form the better, the more valuable, winning combination, the player is more likely to wait until they are satisfied. Hence, to reach the balance, the AI needs to learn calculating and reasoning. Calculating is, since the total number of the cards are solid, players can tell how many cards have been thrown out, which is the ones players can never get. However, calculating is not enough to win since we don’t the rest of the cards are either in other players’ hands or in the shoe. Hence, the AI will learn reasoning, which is to guess what cards the players have by observing what they have thrown out. For example, when one throws out a 9, it basically means the player has already get a 7, 8, 9 in hand since the 7, 8, 9 is already a combination and the other 9 is useless. There are plenty of similar logics that can help the AI to identify what card is possibly in the shoe and avoid to throw cards that make others win. Along with the continuous simulation games, the AI will get better and better, which is Reinforcement Learning.

Summary Update: Each round of games only serves as a data base. At first, the AI will have some initial guesses like the one I mentioned in the previous summary. Then the AI will verify them in the following games. In this process，the AI will give rate these guess and it will utilize the most useful ones. Once the AI has done the evaluate part, the success rate will greatly evaluate.


# AI/ML Algorithms
Reinforcement learning with a model-free, off-policy Deep Q-Network (DQN) algorithm.

Algorithms update: We decide to use decision tree and random forest. They have a common advantage is that they apply to the decision which forced by the rules. Also, they have little calculation so that the decision can be made quickly.


# Evaluation Plan
To evaluate the success of our Sichuan Mahjong AI, we will focus on a combination of quantitative and qualitative metrics. Quantitative evaluation will include metrics such as the AI’s win rate, the average value of its winning combinations, the convergence of its reinforcement learning process, and its time efficiency. Specifically, we will measure the AI’s win rate over a large number of simulated games and compare it to random baseline players and rule-based players. Additionally, we will assess the average value of its winning combinations, ensuring the AI strikes a balance between forming quick wins and achieving high-value combinations. We will also track its learning process by monitoring cumulative rewards and other convergence metrics, while ensuring its decision-making remains computationally efficient during gameplay.
For qualitative evaluation, we will focus on analyzing the AI’s strategic decisions and its ability to adapt during gameplay. We will observe whether the AI avoids making plays that could benefit opponents, effectively balances between forming quick and high-value combinations, and learns to adapt to opponents’ strategies by analyzing their discarded cards. Failure cases will be examined to identify patterns in the AI’s weaknesses, such as over-prioritizing risky strategies or misjudging opponents’ hands. Additionally, we will simulate specific scenarios to verify that the AI correctly applies critical rules, such as deciding when to “peng” or discard a card. As a moonshot goal, we will test the AI against advanced players or in competitive scenarios to evaluate its ability to employ complex strategies, such as bluffing or misleading opponents through its card discards.
To visually represent the evaluation, we will use graphs and charts that illustrate the AI’s win rate improvement and average combination values over time. Comparative analysis against baseline players will be presented through bar charts or similar visualizations. Heatmaps will be used to explain the AI’s decision-making process, such as its reasoning for selecting or discarding specific cards based on the game state. These visualizations will provide an intuitive understanding of the AI’s strategic development and performance.
The evaluation will be conducted on simulated Sichuan Mahjong games adhering to standard rules. The AI is expected to achieve at least a 20% higher win rate than random players and a 10% higher average combination value than rule-based players. These expectations will demonstrate the AI’s ability to balance between winning quickly and forming valuable combinations. By combining both quantitative and qualitative evaluation approaches, we aim to ensure a robust assessment of the AI’s performance and identify potential areas for further improvement.

Evaluation Update: Here is some aspects we think will be useful to evaluate the AI
1. win rate: the AI should win at least 40% - 50% of games. Maybe we will not go the AI-human player stage but at least it should be 50% better than the robot who are playing along with the rules.
2. expected value of each move: During the game, it will print out each move so that we can observe if their move is correct or logical.
3. opponent hand prediction accuracy: We will check if there are any games that the AI's discard make others succeed. In our expect, such situation should be lower than 30%.


#Remaining goals&challenges
During the contiuous game, we found the winning rate indeed greatly elevated. However, sometime when I check the game's print out, I found it tend to be the first to win rather than find the the balance between win quick and win bigger. I think the problem is that it has not enough learning database so that it can't decide whether it can get the tile that will make it bigger. Also, when I decided to use the decision tree, i found that it can't handle the complicate strategy and then to fall into local optimization. In another words, it tend to make sure its tile stay in the situation that has more opportunities to win. Indeed this kind of tiles are easy to win, but it wins too little unless it has a great startup tiles. for example, [1w, 2w, 3w, 3w, 4w, 5w, 6w, 7w, 8w, 9w], [1T, 2T, 3T]. In this occasion, it can win by getting 3w, 6w, 9w. In this most optimistic situation, it can have 9 tiles to win. However, in my aspect, when it get the 3w, 6w, 9w, it should try to keep it and discard T tiles so that it can have a better change to win bigger. 