# Pseudocode for Turkey-Themed Snake Game

## Initialization
1. **Define Constants:**
   - Default food set: `["Pumpkin Pie", "Cranberries", "Turkey Legs"]`
   - Map sizes: `SMALL = 10x10`, `MEDIUM = 20x20`, `LARGE = 30x30`
   - Directions: `UP`, `DOWN`, `LEFT`, `RIGHT`

2. **Initialize Variables:**
   - `mapSize` ← `MEDIUM` (default)
   - `foodOptions` ← `Default food set`
   - `turkeyPosition` ← Center of the map
   - `turkeyLength` ← `1`
   - `direction` ← `NONE`
   - `score` ← `0`

3. **Display Game Setup Menu:**
   - Prompt player to select map size (`SMALL`, `MEDIUM`, `LARGE`)
     - Update `mapSize` based on choice.
   - Prompt player to select Thanksgiving foods or keep defaults.
     - Update `foodOptions` if the player chooses custom items.

4. **Generate Game Map:**
   - Create a grid of size `mapSize`.
   - Randomly place 3 food items from `foodOptions` on the map.

---

## Game Loop
1. **Start Game:**
   - Display `turkeyPosition` on the map.
   - Display the current score.

2. **Input Handling:**
   - Wait for player input to change `direction` (`UP`, `DOWN`, `LEFT`, `RIGHT`).

3. **Update Turkey Position:**
   - Move `turkeyPosition` one grid space in the `direction`.

4. **Check for Food Collision:**
   - If `turkeyPosition` matches a food item:
     - Increase `score` by `10`.
     - Increase `turkeyLength` by `1`.
     - Remove the food item from the map.
     - Randomly spawn a new food item from `foodOptions`.

5. **Check for Collisions:**
   - If `turkeyPosition` collides with the map boundary:
     - End the game.
   - If `turkeyPosition` collides with itself (if `turkeyLength > 1`):
     - End the game.

6. **Render Map:**
   - Clear previous display.
   - Redraw the grid with updated `turkeyPosition` and `foodOptions`.

7. **Game Speed:**
   - Wait for a short delay (e.g., 200ms) before the next iteration.

8. **Repeat Game Loop.**

---

## End Game
1. **Display Final Score:**
   - Show the player's score.

2. **Prompt for Replay:**
   - If the player chooses to replay:
     - Reset variables and start the game again.
   - Else, exit the game.