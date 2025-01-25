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


# AI/ML Algorithms
Reinforcement learning with a model-free, off-policy Deep Q-Network (DQN) algorithm.