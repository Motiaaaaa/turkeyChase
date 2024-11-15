# Test Plan for TurkeyChase Game

## 1. Boundary Cases
- **Number of Players:**
  - TurkeyChase is a single-player game. Boundary cases include testing with:
    - 1 player (minimum).
    - Test what happens if additional players attempt to join (e.g., if the game mode were extended to multiplayer in the future).

- **Map Size:**
  - TurkeyChase offers small, medium, and large map options. Boundary tests should include:
    - Test gameplay on the smallest map (e.g., 10x10 grid).
    - Test gameplay on the largest map (e.g., 30x30 grid).
    - Test the transition when resizing the map (if this feature is allowed).

- **Food Collection:**
  - Boundary tests should include:
    - Collecting the last available food item to ensure new food spawns correctly.
    - Filling the map with the turkey to ensure the game detects when no valid food spawn locations are available.

- **Screen Full:**
  - Test gameplay when the turkey occupies almost the entire map and ensure the game ends correctly when the turkey has no valid moves left.

---

## 2. Design Integration
- **Movement and Collision Testing:**
  - Check that the turkey moves only within the defined map boundaries.
  - Test that the turkey stops growing or moving into its own body (self-collision).
  - Verify the game detects collisions with walls and ends the game correctly.

- **Score and Growth Integration:**
  - Test if collecting multiple food items in sequence correctly increases the turkey’s size and updates the score.
  - Ensure the score reflects the food items eaten, especially with custom-selected food sets.
  - Verify the turkey grows by one segment for each food item eaten.

- **Food Spawning:**
  - Test that food spawns in random, valid locations on the map.
  - Ensure food does not spawn on top of the turkey or outside the map boundaries.

---

## 3. Unit and Logic
- **Turkey Movement:**
  - Check individual turkey movements: moving up, down, left, and right using arrow keys.
  - Ensure the turkey doesn’t move outside the play area or pass through its own body.
  - Test edge cases where rapid directional changes might cause unexpected overlaps.

- **Food Interaction:**
  - Verify the turkey “eats” food when it moves onto the same tile, and the score updates correctly.
  - Test if custom food items integrate correctly into gameplay.

- **Speed Scaling:**
  - Test the speed of the turkey at the initial stage of the game.
  - Ensure the turkey’s movement speed increases gradually as the game progresses (e.g., after eating a certain number of food items).

- **Game-End Logic:**
  - Confirm the game ends correctly when the turkey collides with itself or the map boundaries.
  - Test game-end conditions when no valid moves or food spawn locations remain.

---

## 4. Protect Execution from Bad Input
- **Invalid Key Presses:**
  - If a player presses a key that doesn’t correspond to valid movement, ensure the game ignores the input and continues running smoothly.
  - Test cases where players press conflicting keys simultaneously (e.g., up and down) to ensure no unexpected behavior occurs.

- **Boundary Collisions:**
  - Ensure the turkey does not move outside the map boundaries.
  - Verify the game-over condition activates correctly when the turkey collides with itself.

- **Non-Numeric Input:**
  - If the game requires user input for settings like map size or food selection, ensure non-numeric or invalid input does not crash the game.

---

## 5. Performance Metrics
- **Smooth Gameplay:**
  - Test gameplay across small, medium, and large maps to ensure smooth rendering and responsiveness.
  - Verify that the turkey moves without lag, even as it grows larger or as more food items spawn.

- **Save and Load State:**
  - If supported, test the functionality of saving and loading the game state, ensuring all relevant data—turkey position, food locations, score, and map size—restores correctly.

- **Custom Food Options:**
  - Test the ability to choose a custom set of Thanksgiving food items, ensuring all options spawn correctly during gameplay.
  - Verify default food sets function properly if the player opts not to customize them.


## Features

- **Game Objective**: Control the turkey with arrow keys to eat Thanksgiving food. As the turkey eats, it grows longer.
- **Map Sizes**: The game offers three map sizes:
  - **Small**: A compact play area with less space.
  - **Medium**: A moderate play area with a balance of space and difficulty.
  - **Large**: A large play area with more space, making the game more challenging.

---

## Error Handling

## 6. Handle Other Run-Time Errors
### 1. **Handling Full Screen**
- **Description**: 
  If the turkey runs out of space on the screen (i.e., the blocks fill up the available play area), the game should end, and a "Game Over" message should be displayed. This happens when the turkey collides with the boundaries of the screen or fills the entire available space.
  
- **Implementation**: 
  - The game continuously checks the turkey’s position in relation to the screen's boundaries. If the turkey collides with the screen's edge (i.e., hits the top, bottom, left, or right), the game ends, and the "Game Over" message appears.
  
- **Test Case**:
  - Create a scenario where the screen is nearly full, and ensure that the game ends appropriately when the turkey collides with the boundaries of the screen.
  - Simulate the turkey eating food until it grows large enough to hit the boundaries of the screen. The game should stop and show the "Game Over" message as expected.

- **Example of Game Over Message**:
  - python
  - if turkey_position.x >= screen_width or turkey_position.y >= screen_height:
    - print("Game Over! The turkey ran out of space!")
      - game_over = True