---
layout: post
title: Recreating Conway's Game of Life
date: 2024-09-18 14:02 -0500
categories: [Python, Simulation]
tags: [simulation, pygame, python]     # TAG names should always be lowercase
---

---
# Intro

In my computer programming class recently, the class was introduced to python. Knowing a bit about python already, I decided to undertake some sort of project using a framework that I had never used before, [PyGame](https://www.pygame.org/news). 

A while back, I watched a video by Sam Hogan about his journey to [create a zero-player game](https://www.youtube.com/watch?v=N-BbgqOjIqk) for a Game Jam he participated in. One of the concepts of inspiration for his final design, was a cellular automaton simulation called [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life). Conway's Game of Life can be thought of as enssentially a very rough cellular replication simulations, with very basic rules. 

### Rules

Each cell is either alive or dead. Every replication cycle, the a cell and its neighbors are evaluated one by one, to see wheteher a cell will be alive or dead. 

For cells that are alive:
* If it has less than 2 live neighbors, it will die, as if by underpopulation.
* If it has 2-3 live neighbors, it will continue to stay alive.
* If it has 4 or more live neighbors, it will die, as if by overpopulation.

For cells that are dead:
* If it has exactly 3 live neighbors, it will become alive. 


# Building the Simulation
### PyGame intialization 

The first step in getting the simulation up and running is getting the display window up. Using PyGame and a few online tutorials, I got a basic, black window up and running. This required creating the screen with the right size and then filling it with color. 

### Creating the grid and cells

I created two classes, one for an individual cell and one for the grid. The cell holds its state, x position, and y position. (Although these position data will later become irrelevant in the program, as I just index it instead.) The grid class holds the height and width of the grid and then an array of cells to fill the grid.

I knew early on that I wanted to be able to change the size of the grid, so it just takes the height and width of the screen and divides it by the number of cells. So theoretically, you could have as many rows and columns of cells as you wanted, and could make them any size you wanted.

The program then draws the cells, using the created grid as the argument, and then draws them, the dead cells as black and the white cells as white. After testing it by setting the value of a few cells to be live, I had the grid system up and working!

![Early_Build_With_A_Few_Live_Cells](assets/posts/2024-09-18-recreating-conways-game-of-life/Game_of_Life_Early_Few_Live_Cells.png)

### Developing the Replication System

The next thing needed was to develop the system that looks at each cell and determines whether it will be dead or alive in the next evolution. 

The first thing that I had to do was count the number of live neighbors that each cell had. The way it does this is by getting the index of the cell within the array. It does some math based on the width and height of the cells adding or subtracting 1 here or there to calculate the position of each of the neighbors it touches and then checks whether those cells are on.

It takes the count of its live neighbors, deicdes whether it will be dead or alive in the next iteration based on the rules listed above, and then stores all those values in a new array, which gets replaces the old array at the end of the generation. 


And it works! Below is a gif of a endlessly replicating "spaceship".

![Cells-replicating](assets/posts/2024-09-18-recreating-conways-game-of-life/Cells-replicating.gif)

### Adding the ability to turn cells on or off.
Currently, it's a lot of trouble to turn cells on or off. You have to manually set each of their states in the code. Wanting to make this easier, I added the ability to turn them on and off with the mouse.

It was a little difficult to figure out how to detect contact between the mouse and the cells. Normally in PyGame, you can detect collision between the mouse and cells if each of them are objects with certain properties, specifically being defined as rectangles. But my program didn't do that. Each of the cells were only represented by turning on a specific color based of its position and size, but not the cell itself. 

In order to get it to work, I took the position of the mouse click, and used the x and y values divided by the cell size to find the index of the cell in the array. Once that was found, the code would flip the value of the cell, making live cells dead, and dead cells live.

All that was left was to wait for the simulation to start, which happens when you press the space bar.

![Cells-with-mouse-selection](assets/posts/2024-09-18-recreating-conways-game-of-life/Cells-With-Selection.gif)

### Adding some fun other UI tid-bits
The main function of the simulation is done. All that I wanted to do now is to add a few visual and user tools to flesh it out a bit.

First I added the ability to use the arrow keys to speed up and slow down the simulation. I also added a side panel with a bit of explanation about how the simulation works and some of the controls. Finally, I changed to color of the gird to be creme and gray instead of black and white. It just looks better with the red side bar.

![Full_Game_of_Life_Window](assets/posts/2024-09-18-recreating-conways-game-of-life/Full_GOL_Window.png)

# Conclusion
And that's it. I had a lot of fun with this project, and I'm pretty happy with how it turned out, considering it only took me a few hours. There are still a few problems with it, no doubt. The biggest one is probalbly the fact that because of the way that it counts neighbors cells, any cell on the immediate edge of the screen won't replicate. Because of that, its hardcoded to checks whether a cell is on the edge, and will not count its neighbors if it is. If I come back to this project at all, this is likely one of the first things I would do. However, as long as you dont set any of the edge cells to be live, its really not that big of a deal.