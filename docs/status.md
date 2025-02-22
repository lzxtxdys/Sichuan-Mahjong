Summary Update: Each round of games only serves as a data base. At first, the AI will have some initial guesses like the one I mentioned in the previous summary. Then the AI will verify them in the following games. In this process，the AI will give rate these guess and it will utilize the most useful ones. Once the AI has done the evaluate part, the success rate will greatly evaluate.

Algorithms update: We decide to use decision tree and random forest. They have a common advantage is that they apply to the decision which forced by the rules. Also, they have little calculation so that the decision can be made quickly.

Evaluation Update: Here is some aspects we think will be useful to evaluate the AI
1. win rate: the AI should win at least 40% - 50% of games. Maybe we will not go the AI-human player stage but at least it should be 50% better than the robot who are playing along with the rules.
2. expected value of each move: During the game, it will print out each move so that we can observe if their move is correct or logical.
3. opponent hand prediction accuracy: We will check if there are any games that the AI's discard make others succeed. In our expect, such situation should be lower than 30%.

#Remaining goals&challenges
During the contiuous game, we found the winning rate indeed greatly elevated. However, sometime when I check the game's print out, I found it tend to be the first to win rather than find the the balance between win quick and win bigger. I think the problem is that it has not enough learning database so that it can't decide whether it can get the tile that will make it bigger. Also, when I decided to use the decision tree, i found that it can't handle the complicate strategy and then to fall into local optimization. In another words, it tend to make sure its tile stay in the situation that has more opportunities to win. Indeed this kind of tiles are easy to win, but it wins too little unless it has a great startup tiles. for example, [1w, 2w, 3w, 3w, 4w, 5w, 6w, 7w, 8w, 9w], [1T, 2T, 3T]. In this occasion, it can win by getting 3w, 6w, 9w. In this most optimistic situation, it can have 9 tiles to win. However, in my aspect, when it get the 3w, 6w, 9w, it should try to keep it and discard T tiles so that it can have a better change to win bigger. 

#Resources
https://www.geeksforgeeks.org/decision-tree/
https://medium.com/@samina.amin/deep-q-learning-dqn-71c109586bae
https://www.geeksforgeeks.org/what-is-reinforcement-learning/
https://huggingface.co/learn/deep-rl-course/en/unit0/introduction
https://www.reddit.com/r/reinforcementlearning/