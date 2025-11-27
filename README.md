# DOOM-Arduino
This project is a simplified port of the classic first-person shooter DOOM, adapted to run on an Arduino microcontroller. Due to the extremely limited hardware resources of the Arduino platform, the original game engine was re-implemented using a lightweight pseudo-3D rendering technique based on raycasting. The goal of the project is to demonstrate that even low-power microcontrollers with very small memory can simulate elements of a 3D game through careful optimization and efficient algorithms. 
 
The system renders a basic map with walls and allows the player to move through the environment using physical buttons. Graphics are displayed on a small OLED screen, and all calculations—such as perspective projection, wall height, and collision detection—are performed in real time using integer math to reduce CPU load. 
## Project Purpose
- Optimize software to run on very limited hardware.
- Develop a visual model of a game engine for educational purposes.
- In this project we want to improve our practical skills in robotics.
