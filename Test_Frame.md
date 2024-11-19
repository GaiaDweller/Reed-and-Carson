# 1. Unit Testing the game mechanics
2. Logic Testing the Game Rules and Calculations (Here aswell)
### Movement: 
- Test to see if all of the keys work together, such as w and d making you go up and right at the same time, do for all keys.
- If the player hits a wall, the wall will teleport them to the other side of the map, same y coordinates
### Combat/firing: 
- Test to see if the projectiles fired by the ship correctly generate, and dissapear after they hit something or exit the map to reduce the memory usage of the program.
- Make sure that the projectiles correctly destroy the asteroids/enemies
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
