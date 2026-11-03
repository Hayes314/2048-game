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

這個2048程序在經典玩法基礎上做了不少擴展，主要特色可以歸納為以下幾個方面：

**一、四種玩法模式**
- **經典模式**：標準4×4棋盤，目標2048。
- **限時模式**：默認90秒倒計時，時間條會隨剩餘時間變色（綠→黃→紅），緊迫感更強。
- **障礙模式**：棋盤上會隨機生成4個不可移動的障礙格子，改變滑動路徑。
- **自定義模式**：可自由選擇棋盤大小（3×3到6×6）、目標數字（512到4096）、障礙數量（0到6）和時間限制（無/60秒/90秒/120秒）。

**二、完整的存檔系統**
- 點擊“存檔”可以生成一串Base64編碼的存檔代碼，包含棋盤尺寸、模式、分數、方塊佈局、障礙分布、剩餘時間等完整狀態。
- 複製代碼後可以在任意設備或會話中粘貼讀取，恢復完整進度繼續遊戲。
- 代碼無效時會有紅色提示，避免誤操作。

**三、撤銷與重新開始**
- “復原”按鈕可回退上一步，最多保留20步歷史，同時恢複分數、時間和棋盤狀態。
- “重新開始”完全沿用上一次的配置重新開局，不用重新設置參數。

**四、三語與五主題**
- 支持繁體中文、簡體中文、英文三種界面語言，所有按鈕和提示文字實時切換。
- 提供經典、霓虹、森林、海洋、糖果五套配色主題，方塊顏色、背景和強調色整體聯動。

**五、全屏控制與防誤觸**
- 鍵盤方向鍵/WASD在頁面任意位置都能操作，焦點在輸入框時自動讓位。
- 觸摸滑動也從棋盤擴展到了整個頁面，但會智能避開按鈕、下拉框、對話框等交互控件，不會誤觸。
- 全局阻止頁面滾動和雙擊縮放，滑動時棋盤不會跟著頁面跳動。

**六、流暢的動畫與性能**
- 方塊移動使用 `translate3d` 硬件加速，合併時有彈跳動畫，新方塊有縮放出現動畫。
- 通過 `contain: layout style paint` 和 `will-change` 減少重繪，動畫使用 `requestAnimationFrame` 和回調過期檢查（`actionId`）避免競態。
- 尺寸變化通過 `ResizeObserver` 和 `requestAnimationFrame` 節流處理，佈局計算只在實際尺寸變化時執行。

**七、健壯的遊戲邏輯**
- `canMove()` 從每個方塊出發檢查四鄰，覆蓋空格滑入和同值合併，避免誤判無路可走。
- 障礙物生成時保護中心區域，防止開局即死局。
- 限時模式撤銷時，若剩餘時間已耗盡會恢復一個合理時長，避免撤銷後立刻結束。
- 存檔讀入後也會檢查遊戲狀態，確保不會卡在異常狀態。

整體上，這是一個在經典2048基礎上做了玩法擴展、交互優化和狀態持久化的完整版本，既保留了核心手感，又增加了可玩性和實用性。
