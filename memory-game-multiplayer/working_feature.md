### Overview
This project now supports a “head-to-head” multi-player mode. Two players share the same grid of cards and take turns flipping them over. When a player makes a successful match, they keep their turn. If they fail, the turn switches to the other player. Each player’s score is displayed, and whichever player has the most matches at game end is the winner.

### What Changed
1. **HTML (`index.html`)**  
   - Added a new section in `.game-container` to display both players’ scores and the current player’s turn.  
   ```html
   <div class="player-info">
     <span>Player 1 Score: <span id="player1Score">0</span></span>
     <span>Player 2 Score: <span id="player2Score">0</span></span>
     <p>Current turn: <span id="currentPlayerLabel">Player 1</span></p>
   </div>
   ```
2. **CSS (`project03.css`)**  
   - Introduced a simple `.player-info` style rule to arrange and format the new multi-player scoreboard area (optional aesthetic changes).

3. **JavaScript (`project03.js`)**  
   - Declared new variables to track the current player and their respective scores:
     ```js
     let currentPlayer = 1;
     let playerScores = [0, 0];  // [Player1Score, Player2Score]
     ```
   - Created helper functions `updateScoreDisplay()` and `updateCurrentPlayerDisplay()` to keep the UI in sync.
   - In `checkForMatch()`, if two flipped cards match, increment the current player’s score and **do not** switch turns. Otherwise, switch turns.
   - At the end of the game, a small message also indicates who won (or if it’s a tie).

With these changes, the new multi-player turn-taking feature works as intended.