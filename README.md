# Breakout
***
## A Simple Breakout Game using Canvas
***
## Logic
***
A simple rectangle i.e paddle is drawn on the bottom and a circle i.e ball right over it. The bricks, again rectangles, are drawn using an array. The x and y co-ordinates of all shapes are are constantly monitored. When (x,y) of one shape comes closer to the (x,y) of another shape then needed actions are taken such as moving the ball away, making bricks disappear, bounce etc. ALl of these actions are contained inside the canvas width and height i.e walls of the game. 
## Variables:
***
*  x - Half of canvas width. Used to position the ball. Also used, as different variable, in the bricks object for it's position along x- axis.  
*  y - Value used for positioning paddle from bottom. Again used, as different variable, in the bricks object for it's position along y-axis. 
*  dx - Variable used to change x-value
*  dy - Variable used to change y-vale 
*  radius - Radius of the ball  
*  pos - The value for paddle from the left  
*  rand - An array with random values which is used to comntrol ball's initial direction movement when game starts  
*  won - Variable used when setInterval is called i.e used to stop game when all bricks get destroyed
*  counter - Varibale to store the score
*  rightPress - Variable to determine if right key is pressed
*  leftPress - Variable to determine if left key is pressed
*  brk (rows/cols/len/hgt/space/top/left) - Variables for row count, column count, length of bricks, space between bricks, space from top element, space from left
*  brks[] - array to hold all bricks and values

## Event-Listeners
***
* ("keypress", chkPress, false); - calls function chkPress to see what key was pressed
* ("keydown", keyDownHandler, false); - calls function keyDownHandler to check if key is held.
* ("keyup", keyUpHandler, false); - calls function keyUpHandler to check if key was released.

## Functions:
***
### startGame()
Calls the function that displays the first screen of game. It displays the game name, a box around it and the space bar instruction to start the game
### chkPress() 
Function takes in key pressed as paramter. Executes the function drawall() when key is space bar. The function drawall is used to draw all the shapes in the canvas. The function is called at an interval of 15 milliseconds. This is done so that the movements in the shapes are reflected in the canvas and each time the screen is cleared. The x and y values are changed by adding dx and dy respectively, causing changing in the postion i.e movements. 
### drawBall()
Function that draws a circle. content.arc(x, y, radius, 0, 6) i.e content.arc( x pos, y pos, radius, start angle, end angle). The ball is colored red. Begin and Close path is used to start drawing the arc and end at the point started.
### drawPaddle()
Function that draws the paddle that is used for bouncing off the ball. The paddle is colored black.
### drawBricks()
Function is used to draw the bricks in the screen. Uses the brks[] array and defines each spacing values. Bricks are colored light blue.
### checkVal()
Function that checks the x and y values and alters the values with dx and dy. The simple logic in the function is that if the ball's x and y come near to the walls then the dx and dy values are reversed i.e the movement in that direction is reversed. Thus detects if ball hits sides and top. If the ball hits the paddle i.e the (x,y) lies withing the paddles length and right above it then values are reversed. If the ball crosses it then game over. Also controls the movement of the paddle. 
### collisionCheck() 
Function used to check if the ball hits the brick. The same logic as checkVal() is used. If the ball's co-ordinates lie between the length of any of the bricks then the brick is removed i.e the status code is changed. It is checked for each brick, each time and the only the brick with status code set is drawn. The counter is increased i.e the score variable
### drawScore()
Fucntion is used to draw the score on the screen. Colored white and placed on top of the screen in the middle.
### youLost()
Function used to display the player lost and is colored white.
### youWon()
Function used to display the player won and is colored white.
### keyDownHandler() and keyUpHandler()
Function checks if key held down is left arrow/right arrow and sets rightPress or lefPress to true/false.

##### A last check is made to see if page was reloaded and a new value for ball's inital movement is set
