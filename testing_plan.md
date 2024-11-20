# Test Plan Frame for PONG

## Part 1. Unit Testing the Game Mechanics

- **Movement**: Players should only be able to move the paddle on their side up and down at a constant smooth speed. The paddle initially starts at the center(vertically) but close to the side that pertains to the player. The game should also detect the direction of the curvature of the ball that each player indicates by either swiping or pressing on the direction keys (WASD and arrow keys).

        - The WASD keys correspond with up down left and right arrow keys on the keyboard, and each key will correspond to the direction it represents. For example, the left key and “a” key will curve the ball to a leftward direction, and the up arrow and “w” key will move the paddle upwards.

- **Collision Detection**: The game should detect when the ball hits the paddles or hits one of the horizontal sides of the screen (that will score a point).

- **Gaining abilities**: the game should be able to detect when the ball collects a power up and who hit the ball last to know who the power up goes to.
        - Make sure the power ups have a decent amount of space surrounding its image so that the ball doesn’t “miss it” when it is close enough to collect it.

-**Ball movement**: the ball should be able to curve or/and move linearly and diagonally based on how the player hits it with the “paddle”. After a point is scored, the ball should shoot from the middle to the direction of the player who scored the last point. It starts off at a speed of 10 px per second until a charge up power up is gained and over time the ball speed will increase by 1 px per second every 5 seconds.

## Part 2. Logic Testing the Game Rules and Calculations Description

- **Score calculations**: everytime the ball touches a side of the screen (horizontal), the player on the opposite side gains that point. This will increase their score by one. When one of the scores gets to 11 first, wins the game and the screen stops and puts the paddles and ball to the start position.
        - Score: the score should only increase by one every time the ball touches one of the horizontal sides of the screen.

- **Power-ups**: When a player gets the “charge up” powerup, the ball should immediately return to their side of the paddle and “charge up” for 4 seconds, going faster than the original constant speed (5 px pers second more), and remains that faster speed until another charge up power up is gained. The ball will move with the paddle in this scenario. For the freeze power up, have the opponent’s paddle freeze for 4 seconds. For the invisible paddle power up, have the paddles be invisible for 4 seconds for both players. They will appear every 10 seconds and players are allowed to have multiple power ups at a time.

        - Each power up should only last 4 seconds and do not indicate double scores or extra points, the goal is the same, to score the ball to the opponent’s side.

- **Practice mode**: the same rules should apply to the practice mode, although it will only have one paddle and ball (on the right side). The ball will be thrown from the middle towards the player’s side and after the ball touches the opposite side, the ball will keep respawning the same way until the imputed score is reached.

        - If the ball in practice mode doesn’t touch the opposite wall in 50 seconds, the round of the practice will time out and respawn.

- **Stage select**: the backgrounds should start unlocking one by one for every 4 games the player plays. As they unlock, the player can choose to change the background and it will change it for the main game mode and practice mode.

        - Every background will have a name, if a new background is chose and still matches the old background (meaning it didn’t change), then the program should ask for a background again

## Part 3. Boundary Testing: Edge Cases and Limits Description

- If the power ups glitch out and go more for an extended amount of time, the game will automatically cap the time to only be a maximum of 4 seconds for every power up

- The ball will have a cap speed of 50px per second so that the ball speed isn’t unbearably fast
        - The game will have a variable storing the speed of the ball and will not go above 50 px per second.

- If too many power ups crowd the screen, the game will prevent that by having a max of 7 power ups on the screen at a time. After space for a new power up is made, the game will wait 15 seconds like usual for a new power up to be generated.
        - The game should also have a variable checking how many power ups are on the screen and should not exceed 7 power ups at a time. The randomizer of the power ups will halt when it reaches 7 power ups on the screen and only continue the 10 second wait timer once it is less than 7 power ups

## Part 4. Integration Testing: System Interaction Description

1. Verify that the score updates +1 every time the ball touches one of the horizontal walls
2. Verify that the background chosen is implemented on all the modes
3. Verify that the practice mode doesn’t go over the score the player inputted
4. Make sure that the option chosen on the main menu is the screen that is shown.
5. Check that the ball comes in contact with the paddles and vertical walls while having the correct physics
6. Make sure that the ball can collect power ups correctly.

## Part 5. Handling Bad Input and Run-Time Errors

- If the players press an invalid key(like on the keyboard) ignore the action, it will not do anything.
- If the ball grows to a velocity that supersedes the max velocity, have the game return to the start position (with the same previous scores)

## Part 6: Build a table to present all the test information

### Movement Mecahnics

- Test Data: Mouse click,“WASD” keys, arrow keys, touch
- Expected Outcome: The paddle and ball direction should go in the indicated direction by the keys/mouse/touchscreen

### Collision Detection

- Test Data: Ball scenario
- Expected Outcome: The ball should be able to detect collision on the walls, paddles, and power-ups to collect them

### Score

- Test Data: Player scores
- Expected Outcome: The score should not exceed 11 unless the player is in practice mode and selected a custom max score

### Power up

- Test Data: Time (3, 4, 10 seconds)
- Expected Outcome: The power ups should not be activated longer than 4 seconds and should have the effects and pop-up taken off after 4 seconds

### Invalid Input

- Test Data: “K”. “l”, “2”
- Expected Outcome: These keys should not affect the game at all and should ignore any added action

### Menu Selected

- Test Data: Mouse click or touch screen
- Expected Outcome: The option clicked should have a new screen appear (what the player chose)
