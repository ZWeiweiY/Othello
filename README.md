# Othello_AI

## Description
Othello, a strategy board game for two players, played on an 8×8 uncheckered board with a fixed initial setup of the board.

By implementing artificial intelligence algorithms, such as minimax algorithm and alpha-beta pruning, in a game tree to go for the best move to increase the chance of winning!

### Potential improvements:
Modify evaluation function considering factors, such as Maximum Pieces, Weighted Square, Mobility and Stability Pieces.
Other search methods such as NegaScout (Principle Variation Search), MTD(f) will reduce time and space complexity.

## Why use the Minimax Algorithm?

The minimax algorithm is a robust and reliable method for finding the optimal move in a given position, which is a common choice for developing artificial intelligence (AI) players for two-player games which are deterministic and with perfect information like Othello. 

A deterministic game is a type of game in which the outcome is determined by the initial state of the game and the actions taken by the players. In other words, if two players play the same game from the same starting position, following the same sequence of moves, they will always reach the same final game state.

A perfect information game is a type of game in which all players have complete knowledge of the game state at all times. Each player has access to all of the information that is relevant to making decisions in the game, including the positions of all pieces on the board, the order in which moves have been made, and any other relevant information.

## What is the Minimax Algorithm?

By evaluating all possible moves and countermoves from the current position, the Minimax Algorithm then select the move that leads to the optimal outcome for the player. This is done by assigning a score to each possible move based on its likelihood of leading to a win for the player, and then choosing the move with the highest score. 

The algorithm also considers the countermoves that the opponent might make in response to the player's move, and adjusts the score accordingly.

## How does the Minimax Algorithm work?

The algorithm begins by evaluating the current game state and assigning a score to it based on the likelihood of the player winning from that position.

It then generates a list of all possible moves that the player can make from the current position, and for each move, it generates a list of all possible countermoves that the opponent can make in response.

For each possible move and countermove, the algorithm assigns a score based on the likelihood of the player winning from that position. It then compares the scores for all of the possible moves and countermoves, and chooses the move that leads to the highest score.

The minimax algorithm continues to search and evaluate moves and countermoves in this way until it reaches a terminal game state, such as a win or a draw. At that point, it returns the score for the terminal game state as the result of the search.

## The Evaluation Functions

Using the minimax algorithm to play Othello requires the development of a good evaluation function, which is used to assign a score to each possible move based on its likelihood of leading to a win for the player.

There are many different factors that can be taken into account when designing an evaluation function for Othello, and the specific factors that are included will depend on the goals of the AI player and the strategy it is trying to employ. 

We designed the weighted squares on the board, the smaller the number, the greater the value. The corners hold special importance and should be considered high value options, since they cannot be flanked by the opponent once being captured. The corners also allow a player to build pieces around them and provide stability to the player’s pieces.

Other factors for an evaluation function including Mobility and Stability can also take advantages in certain scenarios.

## Why use α-β pruning?

α-β pruning is an optimization technique that is used to improve the efficiency of the minimax algorithm, which reduces the number of nodes that need to be evaluate and  lead to faster and more efficient searches.

## What is α-β?

α-β pruning works by maintaining two values. α and β, represents the minimum and maximum scores that can be achieved by the player and the opponent.

## How does α-β pruning work?

As the minimax algorithm searches the game tree, it updates the values of α and β based on the scores of the nodes that it evaluates.

If the value of α exceeds the value of β at any point during the search, the algorithm can stop searching the subtree rooted at that node, as the player will not choose a move that leads to a worse outcome.

## Run Test

Test_Opponent.exe is a test program.

Ot8b.c is a modified program (modified segments are commented in c file).

Run.exe is the interface program.

The test method is as follows:
- Put two programs Test_Opponent, Ot8b in the same directory
- Open two command prompt windows and execute Test_Opponent, Ot8b respectively

```bash
run Test_Opponent F 20
run Ot8b S 20
```

- Assuming that Test_Opponent is the first player, first enter F in the window of Test_Opponent, and then enter S in the window of Ot8b. The two programs will switch sequences, and be tested for 20 rounds
- The result will be placed in a txt file result.txt.
- After the test, the winning percentage of the winner will be displayed
- If not, execute Run.exe after execution, you will see the winning percentage of the winner.
