# CubeSim
## Overview
A simple Rubik's Cube simulator and solver built in Python with Pygame with the following features:
* 2d visualisation of Rubik's cube (2 x 2 and 3 x 3).
* Keyboard controls for face turns.
* Parsing scramble strings and performing the scrambles on the cube.
* Generation of animated solutions based on the LBL beginner's method.

<p align="center">
<img src="/cover.webp" width="500">
<p>

### Quick Start
To work on or run this project, start by creating a virtual environment:
```
$ virtualenv venv
```

Activate the virtual environment by running:
```
$ source venv/bin/activate
```

Install the dependencies inside the virtual environment
```
$ pip -r requirements.txt
```

Launch the main graphical user interface
```
$ python3 -m src.main
```

## Implementation ##
### Cube ###
This program uses a relatively simplistic representation of the Rubiks Cube. We simply consider the cube to be an array of 6 2-dimensional arrays, each representing a face of the cube. Each element of these 2-dimensional arrays then represents a sticker on the cube.

A single face turn then can be implemented by:

1. Rotating all elements of the given face by 90 degrees
2. Cycling all the rows/columns that intersect with the given face on all adjacent faces

### Solving ###
The program implements a simplified variant of the LBL beginner's method. This method closely approximates how a normal beginner solver would solve a cube, although without the aid of human intuition. This approach to solving a cube is substantially less move optimal compared to more sophisticated computer-based algorithms, but was chosen due to ease of implementation and relatively low computation cost.
