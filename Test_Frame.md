# 1. Unit Testing the game mechanics
### 2. Logic Testing the Game Rules and Calculations (Here aswell)
### 4. Integration Testing: System Interaction (Here aswell) 
### Movement: 
- Test to see if all of the keys work together, such as w and d making you go up and right at the same time, do for all keys.
- If the player hits a wall, the wall will teleport them to the other side of the map, same y coordinates
### Combat/firing: 
- Test to see if the projectiles fired by the ship correctly generate, and dissapear after they hit something or exit the map to reduce the memory usage of the program.
- Make sure that the projectiles correctly destroy the asteroids/enemies
- Make sure that the game ends when the players health is <= 0
### Asteroids/Enemies: 
- Make sure the enemies have the correct AI to follow and attack the player (Only after 500 Score).
- make sure that the asteroids correctly ungenerate when they leave the map, and dont take away from the total asteroids being spawned unless they are destroyed by the player.
- the asteroids that are missed will regenerate, however at 0.75 of their original value (Player misses 12 asteroids, 9 regenerate, amount that regenerates is rounded up, (1 * 0.75 = 1 asteroid, 2 * 0.75 = 2, 3 * 0.75 = 2)) so the player is still punished for missing asteroids
### Power Ups: 
- Make sure that the power ups correctly spawn in at a small rate when destroying asteroids, they should dissapear after 8 seconds, and the player should have 3 slots for power ups.
- if the player has 3 power ups and they pick up a new power up, the game enters a time stasis and the player decides whether to destroy the new power up for a small amount of currency, or to swap it out with an existing power up (No currency gained when swapping), the power up swapped out is destroyed.
- Make sure that power ups can compliment eachother, such as making buckshot with double blasts = 2 buckshot blasts.
### Difficulty System: 
- The player will select a starting difficulty, (1,2,3) this formula is used to determine the amount of asteroids that will spawn per round.
- Formula for spawning asteroids is related to the difficulty * a random integer (minimum of 20 per round).
### Round end:
- After each round finishes (player kills the predesignated amount of asteroids, ((Total Asteroids - Missed Asteroids) + (Missed Asteroids * 0.75)) The player will visit the shop.
- The shop contains player upgrades, health restoration and more.
- Check each items effect and set a max amount of each item to be purchased (health restoration will have no limit)
### Score/Currency:
- Make sure that the score increments per asteroid and enemy destroyed
- make sure that the currency increments per asteroid and enemy destroyed.
### Leaderboard:
- Make sure that the player knows that when they are offline the score will not be updated to the leaderboard until they reconnect to the internet.'
- Make sure the Leaderboard is correctly updated, update every 24 hours to decrease the amount of requests on the servers.

# 3. Boundary Testing: Edge Cases and Limits
### Maximum Score:
- There will be no maximum score, the score will originally be 0000, once the player breaks 9999 the score will add another digit and become 10000, this can happen infinitely, making the maximum score not an issue
### Minimun Score:
- Not possible to go below 0 (dying before hitting any asteroids)
### Piercing:
- When the player has the piercing upgrade, the bullets correctly update the score and dissapear after destroying each asteroids.
- Bullets pierce through +1 asteroids/enemies per upgrade (maximum of 5)
### Asteroid Spawning:
- Set maximum of asteroids on the screen to 15, slowly spawn in as the player destroys, minimum on screen is 1 (before ending the round)
### Correctly handle death:
- If players health is negative or 0, end the game.
### Check if the power ups function correctly:
- If the player picks up multiple at once, does the game correctly handle it?

# 5. Handling Bad Input and Run-Time Errors:
### Bad Input:
- Non-existent, all keys that dont have an input will be registered to do nothing
### Runtime-Errors:
- If the game doesnt respond for over 5 seconds, the game will automatically call the pause menu (to save the player).
- if the game dooesnt load after 15 seconds (opening the app, or starting a game) the app will ask to check internet connection and give a choice to enter offline mode.
### Error handling:
- If the game crashes the program will gather a quick snapshot of the players progress, trying to save as much as possible to give the player a chance to continue their game even after a crash.

| Test Case   | Test Data   | Expected Outcome  |
|------------|------------|------------|
| Movement | w, a, s, d | Check if w moves up, a moves left, s moves down, and d moves right, they all can work in congruency. |
| firing | 1 blast, 2 blasts, 5 blasts, 15 blasts | The game will create each blast with the correct piercing amount and delete them after they exit the map or hit an asteroid |
| Score | 1, 50, 5000, 50000000 | The game will display the correct score and update it to the leaderboard |
| Power Ups | Each Power Up | Each power up works as expected, and works with some others to create a dual affect|
