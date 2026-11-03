<h1>2048 game</h1>

This 2048 program has made a lot of expansions on the basis of the classic gameplay. The main features can be summarized in the following aspects:

**I. Four modes of playing**

- **Classic Mode**: Standard 4×4 chessboard, target 2048.

- **Time-limited mode**: The default 90-second countdown, and the time bar will change color with the remaining time (green → yellow → red), with a stronger sense of urgency.

- **Obstacle mode**: 4 immovable obstacle squares will be randomly generated on the chessboard to change the sliding path.

- **Custom mode**: You can freely choose the size of the chessboard (3×3 to 6×6), the target number (512 to 4096), the number of obstacles (0 to 6) and the time limit (none/60 seconds/90 seconds/120 seconds).

**II. Complete archiving system**

- Click "File" to generate a string of Base64-encoded archive codes, including the complete status of chessboard size, pattern, score, block layout, obstacle distribution, remaining time, etc.

- After copying the code, you can paste it into any device or session and read it, restore the full progress and continue the game.

- When the code is invalid, there will be a red prompt to avoid misoperation.

**III. Cancel and restart**

- The "Restore" button can go back to the previous step, keep the history of up to 20 steps, and restore the score, time and chessboard status at the same time.

- "Restart" completely follows the previous configuration to restart the game, and there is no need to reset the parameters.

**IV. Three languages and five themes**

- Support three interface languages: traditional Chinese, simplified Chinese and English, and all buttons and prompts can be switched in real time.

- Provide five sets of color matching themes of classic, neon, forest, ocean and candy, and block colors, background and emphasis colors are linked as a whole.

**V. Full-screen control and anti-mistake contact**

- The keyboard arrow keys/WASD can be operated anywhere on the page, and the focus will automatically give way when the focus is in the input box.

- Touch sliding is also extended from the chessboard to the whole page, but it will intelligently avoid buttons, drop-down boxes, dialog boxes and other interactive controls, and will not be touched by mistake.

- The whole situation prevents page scrolling and double-clicking to zoom, and the chessboard will not jump with the page when sliding.

**VI. Smooth animation and performance**

- Block movement uses `translate3d` hardware acceleration. There is a bounce animation when merging, and the new block has a zoom animation.

- Reduce repainting through `contain: layout style paint` and `will-change`, animation uses `requestAnimationFrame` and callback expiration check (`action Id`) Avoid competition.

- Size changes are processed by `ResizeObserver` and `requestAnimationFrame` throttling, and the layout calculation is only executed when the actual size changes.

**7. Strong game logic**

- `canMove()` Check the four neighbors from each square, cover the space slip in and merge with the same value, so as to avoid misjudgment.

- Protect the central area when obstacles are generated to prevent death at the beginning.

- When the time-limited mode is canceled, if the remaining time is exhausted, a reasonable time will be restored to avoid the end immediately after the cancellation.

- After the archive is read in, the game status will also be checked to ensure that it will not be stuck in an abnormal state.

Overall, this is a complete version of gameplay expansion, interaction optimization and state persistence on the basis of the classic 2048, which not only retains the core feel, but also increases playability and practicality.
