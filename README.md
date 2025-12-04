# DOOM-Arduino
This project is a simplified port of the classic first-person shooter DOOM, adapted to run on an Arduino microcontroller. Due to the extremely limited hardware resources of the Arduino platform, the original game engine was re-implemented using a lightweight pseudo-3D rendering technique based on raycasting. The goal of the project is to demonstrate that even low-power microcontrollers with very small memory can simulate elements of a 3D game through careful optimization and efficient algorithms. 
 
The system renders a basic map with walls and allows the player to move through the environment using physical buttons. Graphics are displayed on a small OLED screen, and all calculations—such as perspective projection, wall height, and collision detection—are performed in real time using integer math to reduce CPU load. 
## Project Purpose
- Optimize software to run on very limited hardware.
- Develop a visual model of a game engine for educational purposes.
- In this project we want to improve our practical skills in robotics.
  
## Components
- Arduino Uno
- Wires
- Buttons
- Buzzer
- OLED display
- BreadBord

## Work Process
Our project began when we found a similar project on GitHub that provided all thenecessary files and libraries for the DOOM port. The repository contained:
- A working game engine written in C/C++ for Arduino.
- Libraries for controlling the OLED display and handling input from physical buttons.
- A complete circuit diagram showing how to connect the Arduino to the buttons and the display. We downloaded the necessary libraries and files directly fromthe GitHub repository, and followed the provided instructions. After that, we only needed to buy the missing components, assemble the hardware, and modify the code to suit our specific display model.
### 1. Hardware Connection
The GitHub repository provided a detailed wiring diagram that showed how to connect the buttons for user input and the OLED display to the Arduino. We followed this schematic and assembled the circuit as instructed. The buttons were connected to the digital pins of the Arduino, while the OLED display was connected via the I2C interface, reducing the number of wires needed.
### 2. Game Engine Development
- doom-nano.ino — main Arduino sketch that initializes the system, runs the game loop, and coordinates all modules.
- display.h / display.cpp — handles drawing graphics to the OLED screen (SSD1306 driver), including sprites and text rendering.
- SSD1306.h / SSD1306.cpp — low-level driver for the SSD1306 OLED display, including pixel buffers and communication over I2C.
- TWI_Master.h / TWI_Master.cpp — implementation of the I2C communication layer used to control the display.
- input.h / input.cpp — processes user input (buttons, controls) and converts it into actionable game commands.
- sound.h — manages sound effects and simple audio output.
- entities.h / entities.cpp — defines game objects, their properties, updates, and interactions.
- sprites.h — contains sprite data used for rendering characters and objects.
- types.h / types.cpp — defines core data structures, types, and utility functions used across modules.
- constants.h — global settings, screen size, frame timing, and configuration values.
- level.h — level data and map layout.
- README.md — documentation describing how to run and configure the project.

  ## Challenges and Optimization
One of the main challenges we faced during development was the display selection. At first, we used a 1.3-inch 240×240 SPI OLED, but the game engine was originally designed for the SSD1306 driver. The rendering logic, buffer structure, and library functions were all tightly coupled to SSD1306.h, which made adapting the engine to a different display nearly impossible without rewriting the entire graphics system. Because of this, we decided to switch to the correct SSD1306-compatible screen instead of modifying the engine.  

In terms of optimization, we removed the “Back” button from the control scheme. It was rarely used, added unnecessary complexity, and was not comfortable in gameplay. Eliminating it simplified input handling and improved overall usability. 
