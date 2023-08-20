## About modeling game model

This chapter lists some game logic. The idea is to be able to use elements of such list as input for design exercises. 
All the games in this chapter requires an 2D grid.

In a second step adding an UI Layer based on Bloc is left to the reader following for example the tutorial.


### Minesweeper

Game field: The field is composed of cells: a cell may be clean or suspected to contain a bomb. 
At the beginning the status of a cell status is unknown or closed.
Once a cell is open, a clean cell displays the number of its adjacent bombs. 
Using this information closed cells can be tagged as suspected to contain a bomb. 


Goal: The use should identify the bombs using hints based on the number of adjacents bomb in the 8 directions. 

The user has two kinds of action: declare that a cell contains a bomb or declare that it is free and asking for a validation.

- Free cell declaration: If the user is wrong and there was a bomb then he loses the game. If the user is right then the cell displays the number of adjacent bomb around the cell. 
- Bomb declaration: when a cell is 

When all the cells have been revealed or marked as a bomb, the game proceeds to the validation. 
If the bombs are correctly identified the user wins.

![ Minesweeper: identifying mines based on the number of adjacent cells containing a bomb.](figures/MineSweeper2.png width=80&label=mine)







### 2048

![ 2048 ](figures/2048.png width=40&label=2048)

### Lightout

![ LightOut or Quinto ](figures/Quinto.png width=60&label=quinto)

### Memory

![ Memory ](figures/Memory.png width=40&label=Memory)

### SlideOut


![SlideOut: Elements can slides in one direction but are blocked by others. The goal is to get the red element out.](figures/SlideOut.png width=60&label=GameOne)

### Laser game

The game will be played on a grid. We will imagine having a laser beam that can be activated by the user. This will fire into the grid from a specific location. The laser beam will always fire from the bottom edge underneath the first column of cells (marked by the arrow in Figure *GameOne*). As the laser beam traverses inside our grid it can hit deflecting mirrors. These mirrors will divert the laser beam's direction as it travels. Ultimately the beam should hit a target location inside our grid.  Once the laser is fired we will see how the cells guide the laser to a destination. 

The cells of our grid will either be blank, have a target (shown as a circle here) or a deflecting mirror. The mirrors may be oriented in either of two ways, leaning left or right.

![(a) Starting from its origin, the laser beam should reach the target. (b) Rotating a mirror changes the path of the laser beam](figures/Laser-2-Concept-MirrorRotation.png width=60&label=GameOne)

Initial locations and orientations of the mirror cells will be randomly controlled by the game. In *GameOne*(a) the mirrors yield a correct result. However, the user has control over mirror rotation and position (to a certain amount). The user can click on a mirror cell and cause the mirror cell to rotate 90 degrees. This could alter the laser's direction as shown by Figure *GameOne*(b). When the laser hits a grid wall, its path ends.

Since, initially, this is a solitaire game, it becomes more interesting to have the user manipulate the mirrors to find the longest possible path to the target.  

The user may click on a mirror cell and cause it to slide one grid-cell in a vertical or horizontal direction. Note that a mirror cell cannot move through the grid walls nor through another mirror cell nor the target cell. In this way the user can adjust the mirror cells to get an intermediate result as shown by Figure *LongerPathOne*.

%+Finding a longer path, first move, slide %mirror.>file://figures/2-LongerPath1-Slide.png|width=60|label=LongerPathOne+

A further intermediate result is produced by rotating the mirror shown in Figure *LongerPathTwo*.

%+Finding a longer path, second move, rotate %mirror.>file://figures/2-LongerPath2-Rotate.png|width=60|label=LongerPathTwo+

%+Finding a longer path, last move, rotate %mirror.>file://figures/2-LongerPath3-Slide.png|width=60|label=LongerPathThree+

As a last step, one more mirror is moved to get the laser back to the target cell as shown in Figure *LongerPathThree*. This time the path of the laser is longer than before. And of course it was strictly a random coincidence that the initial cells configuration already provided a correct path for the laser.

That's the general idea. We can add laser cell-path counters and other game instrumentation as we develop.


### Same game

![ SameGame : collapsing columns by removing one by one colored of the cell of the same color. ](figures/SameGame.png width=40&label=mine)

### Nonogram

### Taquin

### 