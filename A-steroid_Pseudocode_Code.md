# Game Mechanics

Include a Math library  
Include a Random library  
Include a Game Development Library  

Initialize `player_coordinates` as `[0, 0]`  
Initialize `difficulty` as `1`  
Initialize `player_angle` as `0`  
Initialize `player_hits` as `0`  

Async function for UP and Down  
    Forever loop  
        If W pressed add 1 to `player_coordinates[1]`  
        If S pressed subtract 1 from `player_coordinates[1]`  

Async function for RIGHT and LEFT  
    Forever loop  
        If D pressed add 1 to `player_coordinates[0]`  
        If A pressed subtract 1 from `player_coordinates[0]`  

Async function for rotation  
    Forever loop  
        `angle = arctan((mouse_y - player_coordinates[1]) / (mouse_x - player_coordinates[0]))`  
        Return angle  

Async function for Firing  
    Forever loop  
        If LEFT CLICK  
            Create laser entity at `player_coordinates`  
            Laser_Angle = player_angle  
            While laser coordinates within screen  
                Increase laser_coordinates[0] by 1  
                Increase laser_coordinates[1] by `tan(Laser_Angle)`  
                Wait 100 milliseconds  

Async function for asteroid movement  
    When spawned  
        While asteroid is on screen  
            Add 1 to `asteroid_coordinates[0]`  
            Add `(player_coordinates[1] - asteroid_coordinates[1]) / (player_coordinates[0] - asteroid_coordinates[0])` to `asteroid_coordinates[1]`  
            Wait 100 milliseconds  

Forever loop  
    Display player ship at `player_coordinates` with rotation of Rotation function  
    Run Ship Firing function  
    Run Asteroid Movement function  

    If asteroid touches laser  
        Despawn asteroid  
        Play explosion animation at asteroid coordinates  
        Add 1 to score  
        Add 1 to money  

    If 0 asteroids on screen  
        Add 1 to difficulty  
        Spawn `(random number between 0.0 and 1.0) * difficulty` asteroids  
        Spawn random number between 0 and 3 power-ups  

    If difficulty > 10  
        Spawn random number between 0 and 5 enemy ships  

    If player touches asteroid, enemy ship, or enemy laser  
        Add 1 to `player_hits`  

    If `player_hits` > 5  
        Despawn all entities  
        Display "You're Dead" screen  
        Print score to screen  
        Wait 5 seconds  
        Return to home screen  
