# Game Mechanics

Include a Math library  
Include a Random library  
Include a Game Development Library  

Initialize `player_coordinates` as `[0, 0]`  
Initialize `difficulty` as `1`, `2`, or `3` depending on the players selection.
Initialize `player_angle` as `0`  
Initialize `player_hits` as `0`  

Async function MoveUpDown  
&nbsp;&nbsp;&nbsp;&nbsp;Forever loop  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If W pressed  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Add 1 to player_coordinates[1]  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If S pressed  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Subtract 1 from player_coordinates[1]  

Async function MoveRightLeft  
&nbsp;&nbsp;&nbsp;&nbsp;Forever loop  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If D pressed  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Add 1 to player_coordinates[0]  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If A pressed  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Subtract 1 from player_coordinates[0]  

Async function Rotation  
&nbsp;&nbsp;&nbsp;&nbsp;Forever loop  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;angle = arctan((mouse_y - player_coordinates[1]) / (mouse_x - player_coordinates[0]))  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Return angle  

Async function Firing  
&nbsp;&nbsp;&nbsp;&nbsp;Forever loop  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;If LEFT CLICK  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Create laser entity at player_coordinates  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Laser_Angle = player_angle  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While laser coordinates within screen bounds  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment laser_coordinates[0] by 1  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment laser_coordinates[1] by tan(Laser_Angle)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Wait 100 milliseconds  

Async function AsteroidMovement  
&nbsp;&nbsp;&nbsp;&nbsp;When spawned  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While asteroid is on screen  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment asteroid_coordinates[0] by 1  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment asteroid_coordinates[1] by (player_coordinates[1] - asteroid_coordinates[1]) / (player_coordinates[0] - asteroid_coordinates[0])  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Wait 100 milliseconds  

Forever loop  
&nbsp;&nbsp;&nbsp;&nbsp;Display player ship at player_coordinates with rotation from Rotation function  
&nbsp;&nbsp;&nbsp;&nbsp;Run Ship Firing function  
&nbsp;&nbsp;&nbsp;&nbsp;Run Asteroid Movement function  

&nbsp;&nbsp;&nbsp;&nbsp;If asteroid touches laser  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Despawn asteroid  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Play explosion animation at asteroid coordinates  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment score by 1  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment money by 1  

&nbsp;&nbsp;&nbsp;&nbsp;If no asteroids on screen  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment difficulty by 1  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Spawn (random number between 0.0 and 1.0) * difficulty asteroids  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Spawn random number of power-ups (0-3)  

&nbsp;&nbsp;&nbsp;&nbsp;If difficulty > 10  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Spawn random number of enemy ships (0-5)  

&nbsp;&nbsp;&nbsp;&nbsp;If player touches asteroid, enemy ship, or enemy laser  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Increment player_hits by 1  

&nbsp;&nbsp;&nbsp;&nbsp;If player_hits > 5  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Despawn all entities  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Display "You're Dead" screen  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Print score to screen  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Wait 5 seconds  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Return to home screen  
