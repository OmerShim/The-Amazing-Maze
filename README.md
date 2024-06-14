# The-Amazing-Maze Game
# Maze game OOP Project!

# Omer Shimoni & Or Meir Sarfati

# General Explanation -
In this project, we created a cat and mouse maze game in C++ using the SFML graphic library, using the principles we learned in object-oriented programming with an emphasis on encapsulation and the correct use of inheritance and polymorphism.

# List of all files:

# headers: (.h files)
Cheese.h - This class holds the declarations for functions used to manage conflicts. 
AddLifePresent.h- This class holds the declarations for functions used to manage conflicts.
Door.h - This class holds the declarations for functions used to manage conflicts.
FreezeCatPresent.h - This class holds the declarations for functions used to manage conflicts. 
IncreaseTimePresent.h - This class holds the declarations for the functions used to manage collisions.
Key.h - This class holds the declarations for functions used to manage conflicts. 
KillCatPresent.h - This class holds the declarations for functions used to manage conflicts. 
Wall.h - This class holds the declarations for functions used to manage conflicts. 
Cat.h - This class holds the declaration for managing the collisions with the cat and in addition the declarations for the functions used to move the cat.
Mouse.h - This class holds the implementation of the collision between the mouse and any object on the board and in addition declarations about functions related to the objects.
MovingObject.h - This class holds the declarations for the functions responsible for moving objects and inherits for any object that is not static.
Controller.h - This class serves as a sort of mediation between the different classes and is responsible for the functionality of the game components.
GameObject.h - This class is an abstract class through which all collisions are managed. 
Level.h - This class holds part of the data structures that enable the game to progress and is also responsible for loading the level and drawing it. 
Menu.h - This class is responsible for the game menu and also starts the entire game.
ResourceManager.h - A singleton class that serves as a resource class that serves the entire program .
Stats.h - This department is responsible for the information bar at the bottom of the screen and is responsible for presenting the user with the required information throughout the course of the game. 

# Cpp:
Cheese.cpp - This file implements collision handling logic for a cheese object using polymorphism. 
AddLifePresent.cpp - This file implements collision handling logic for an object adding life to the mouse using polymorphism. 
Cat.cpp - This file contains the cat movement algorithm.
Door.cpp - This file implements collision handling logic for a door object using polymorphism. 
FreezeCatPresent.cpp - This file implements collision handling logic for a cat freeze object using polymorphism. 
IncreaseTimePresent.cpp - This file implements collision handling logic for a time increment object using polymorphism. 
Key.cpp - This file implements collision handling logic for a key object using polymorphism. 
KillCatPresent.cpp - This file implements collision handling logic for a cat elimination object using polymorphism. 
Mouse.cpp - This file implements collision handling logic for a mouse object using polymorphism and also contains the mouse movement.
MovingObject.cpp - This file realizes the properties of the moving objects, i.e. directional displacements and speed.
Wall.cpp - This file implements collision handling logic for a wall object using polymorphism. 
Controller.cpp - This file contains the functions that affect the game data such as gifts and time and also implements drawing objects on the board.
GameObject.cpp - This file contains the relevant functions for objects that do not move on the board such as the map elements and objects. 
Level.cpp - This file is responsible for loading the level from a text file and is responsible for drawing it on the screen using a general vector that uses polymorphism.
Main.cpp - This file starts the game by calling the function that starts the game.
Menu.cpp - This file is responsible for the game menu, its function and drawing on the screen.
ResourceManager.cpp - This file contains an implementation of hash tables containing game components such as textures and sounds.
Stats.cpp - This file contains the line of information that appears during the game at the bottom of the screen and is updated according to the progress of the game.


# Main data structures (and their locations):
Level.h -
A vector into which all the existing objects in the game are loaded and through which an appeal is made to each of them through polymorphism.
In addition, this class contains a Boolean matrix that represents obstacles on the map and is used by the cat's algorithm.
ResourceManager.h -
Hash table responsible for all textures in the game.
Hash table responsible for all sounds in the game.
The hash tables optimize the runtime for texture/sound retrieval whenever such an operation is required.

# Noteworthy algorithms:
Cat.h - we decided that the movement of the cats will be done using the BFS algorithm.
High School :
The various objects in the program:
Gifts: gift of extra life, gift of freezing a cat, gift of extra time, gift of killing a cat.
Objects: key, cheese.
Obstacles: door, wall.
Characters: cat, mouse.
Each of these objects is responsible for himself and himself only and his role is to take care of his own effectiveness in the game.
Regarding the way of communication between the objects in the game -
The communication between the objects is carried out using double dispatch because it is not known which object we would like to communicate with at each stage, the communication method taught in class is chosen.

Known bugs:
In cats: the cats in their movement 'go up' partially on the walls. With the help of Michal, we were able to understand the source of the problem (for the cat, the displacement algorithm refers to the pixel that is the center of the cat, but for the road - for it, all the pixels that are in the space between two walls are normal pixels to pass, and thus a situation is created in which the cat chooses the pixel closest to the wall and is displayed like this whose half exceeds it), we were unable to write the code differently in a way that would solve the problem.
