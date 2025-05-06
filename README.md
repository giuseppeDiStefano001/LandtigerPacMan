# LandtigerPacMan
In Keil µVision, used the LANDTIGER board to implement a Pac-Man game

# Pac-Man History 
Pac-Man, originally known as Puck Man in Japan, is a maze video game developed and released by Namco in 1980. The game was later released in North America by Midway Manufacturing. The inspiration for the Pac-Man character came from a pizza with a slice removed, and the game's characters were designed to be cute and colorful to appeal to younger players. In the game, Pac-Man eats the pills scattered throughout the maze to make points, while avoiding the ghosts that chase him. You can try online Pac-Man 

# How to install
1) 


# Specifications

Use the display of the LandTiger to show the labyrinth for Pac-Man.
- the labyrinth fits exactly 240 Standard Pills. Please keep the “central” box, as it may be used later.
- the current Score of the game and the Remaining Lives and a Countdown timer are printed on the landTiger
- As for the game mechanics I was requested to integrate the following rules:
Spec. 1) Fill the Labyrinth with 240 Standard Pills.

Spec. 2) Generate 6 Power pills in random position. These pills replace the Standard Pill in their
         location. You have to implement the randomness of Power Pills appearance both for the position
         and time.
         
Spec. 3) The player can move Pac-Man through the joystick. Once the direction is chosen (left, right, up, down), Pac-Man continues to go in the specified direction until:
          a. The player selects a new direction through the joystick.
          b. Pac-Man encounters a wall, in this case he stops and wait for player input.
-Freely choose Pac-Man speed (just make it “playable”)

Spec. 4) When the player reaches the central 'teleport' locations (refer to the figure), Pac-Man exits from one side and re-enters from the other side while maintaining 
         the original movement direction.
         
Spec. 5) Each time Pac-Man goes on top of a Pill, it eats it and the Score counter increase by 10 (Standard Pills) or 50 (Power Pills).

Spec. 6) Every 1000 points, Pac-Man earns a new life (from a starting count of 1).

Spec. 7) INT0 Pause the game: Place a “PAUSE” message in the middle of the screen and stop Pac-Man movement.
         Pressing again INT0 resume the game (delete the Pause message and resume movement). The game starts in “PAUSE” mode.
         
Spec. 8) The Countdown starts from 60 seconds and count down up to 0.

Spec. 9) Once the player cleans up the labyrinth (by eating all the Pills), Pac-Man stops moving and a 'Victory!' screen is shown.

Spec. 10) If the countdown timer expires before all pills have been eaten, a “Game Over!” screen is shown instead.
