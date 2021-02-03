# Snake
Planning in the game of the snake
Snake game in Python based on https://www.edureka.co/blog/snake-game-with-pygame/

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)

## General info
Tasks:
- preparation of several environments based on the game of snake
- implementation of the selected traffic planning method
- use of information returned by the planner to control the hose


Assumptions:
- Finding the optimal path.
- Checking the operation of the algorithm at the highest snake speed.


Execution:
- Using the A * algorithm to find the optimal global path.
- Create a local planner avoiding obstacles in the absence of a global path.
- Both planners work on separate threads, in parallel.


How it works?
1. Drawing food
2. Launch of the global planner A *.
3. While the algorithm is running on a separate thread, the snake uses the local planner.
   - When A * finds a way to eat, the snake's current position is linked to the found path.
   - When it finds no way to eat, the snake moves according to the local planner.
  
  
Local Planner Asumptions:
 - The snake is always trying to move forward.
- If an obstacle is detected two fields in front of the snake's head, the possibility of changing direction is checked. To this end, the condition of two fields ahead is checked for each direction.
- If there is an obstruction, two forward squares for each direction, one forward squares condition is checked.
- When there is no way to move, the snake must die, and it is game over.


Additional functions:
- Snake's position is checked every 5 steps to find a new, optimal path.
- Prevention of the "invisible snake tail" effect by updating the snake position with each route search attempt.


## Technologies
Project is created with:
* Python version: 3.7.4
* Pygame version: 1.9.6
	
## Setup
To run this project, launch file main with argument that selects your map:

```
$ python main.py number_of_map
```




