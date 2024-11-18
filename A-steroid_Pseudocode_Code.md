Include a Math library 
Include a Random library 
Include a Game Development Libary

Initialize player coordinates variable starting as [0,0]
Initialize difficulty as 1
Initialize player angle as 0
Initialize player hits as 0

Asynchronous function for UP and Down
	Forever loop
		If W pressed add 1 to player coordinates the second index
		If S pressed add -1 to player coordinates the second index

Asynchronous function for RIGHT and LEFT
	Forever loop
		If D pressed add 1 to player coordinates the first index
		If A pressed add -1 to player coordinates the first index

Asynchronous function for rotation
	Forever loop
		angle = to inverse tan((mouse Y coordinate - Player Y coordinate) / (mouse X coordinate - Player X coordinate))
		return angle
		

Asynchronous function for Firing
	Forever loop
		If LEFT CLICK
			Create laser entity at player coordinates 
			Laser Angle = Player Angle
			While Coordinates in a range of screen
				Increase Laser X Coordinate value by 1
				Increase Laser Y Coordinate value by tan(Laser Angle)
				wait 100 milliseconds

Asynchronous function for asteroid movement
	When spawned 
		While the asteroid is on screen
			Add 1 to the astroid coordinate 
			Add (Player Y Coordinate - Asteroid Y Coordinate) / (Player X Coordinate - Astroid X Coordinate) to asteroid Y coordinate 
wait 100 milliseconds

Forever Loop
	Display Player Ship at player coordinates with a rotation of the Rotation Function
	Ship Firing Function
	Astroid Movement Function
	
	If Astroid touches Laser
		Despawn Asteroid
		Play Explosion Animation at asteroid coordinates
		Add 1 to score
		Add 1 to money

	If 0 asteroids on screen
		Add 1 to Difficulty 
		Spawn ((random number between 0.0 and 1.0) x Difficulty) Asteroids
Spawn random number between 0-3 power-ups 
If Difficulty is greater than 10
	Spawn random number 0-5 enemy ships
		
	
	If the Player touches an astroid, enemy ship, or enemy laser
		Add one to player hits

	If Player Hits exceeds 5
		Despawn all entities
		Display your Dead screen
		Print score to screen
Wait for 5 seconds  
		Return to home screen
