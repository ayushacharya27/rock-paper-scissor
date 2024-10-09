# Rock Paper Scissors Game with MediaPipe and Arduino

This project implements an unbeatable Rock Paper Scissors game where a computer, powered by Google's MediaPipe for hand tracking, always wins. The computer "reads" your hand gestures via a camera and communicates with an Arduino to move servos that control a physical hand, replicating the moves.

## Project Overview

The program uses MediaPipe's hand-tracking feature to identify hand gestures for Rock, Paper, and Scissors. Once a gesture is detected, the program communicates with an Arduino via serial communication to move servo motors that control a cardboard hand, defying the user's hand gestures.

### Key Features
- **Unbeatable Computer**: The computer is programmed to always win by showing a counter gesture to the one recognized.
- **MediaPipe for Gesture Recognition**: Hand gestures are tracked using MediaPipe's predefined coordinates without requiring custom training.
- **Arduino-Controlled Servos**: The physical hand, controlled by servo motors, displays the computer’s chosen gesture.
  
## Components Used

- **Arduino Uno**: To control the servos that move the cardboard hand.
- **Python**: The main programming language used for gesture recognition, serial communication, and controlling the game. Key libraries include:
  - `mediapipe`: For hand tracking and gesture detection.
  - `serial`: To communicate with the Arduino.
  - `OpenCV`: For camera input and video processing.
- **Servo Motors**: Used to control the movements of the cardboard hand.
- **3-Fingered Hand Replicating the Original Hand (Cardboard Cutouts)**: A cardboard hand connected with rubber bands to hold the gestures in place.

## How it Works

1. **Hand Gesture Detection**: 
   - The program tracks hand gestures using MediaPipe's hand-tracking functionality.
   - For each gesture (Rock, Paper, Scissors), specific conditions are checked based on the coordinates of the finger tips and joints:
     - For **Paper**, the tip of all fingers and the middle joint should be above the MCP (metacarpophalangeal) joint.
     - Similar logic is used for **Rock** and **Scissors**.
   
2. **Serial Communication with Arduino**: 
   - After detecting the gesture, the program communicates with the Arduino using serial communication.
   - The Arduino controls the servo motors, which move a cardboard hand to show the computer's counter gesture.

3. **Cardboard Hand Setup**:
   - A 3-fingered hand is cut out of cardboard to replicate human hand gestures for Rock, Paper, and Scissors.
   - Rubber bands are attached to keep the fingers in position, while servos move them to mimic different gestures.
   - A resisting cardboard is placed behind the hand to ensure proper movement.

## Setup Instructions

1. **Hardware Setup**:
   - Cut out a cardboard hand with 3 fingers that can show Rock, Paper, and Scissors gestures.
   - Connect the cardboard fingers using rubber bands to keep them stretched out.
   - Mount the hand onto a base with servos attached to control each finger.
   - Connect the servos to an Arduino Uno.

2. **Software Setup**:
   - Install Python and the following libraries:
     ```bash
     pip install mediapipe opencv-python pyserial
     ```
   - Clone or download this repository to get the Python code.

3. **Running the Program**:
   - Ensure your Arduino is connected to your computer.
   - Run the Python script to start the hand-tracking and game logic:
     ```bash
     python rock_paper_scissors.py
     ```

4. **Game Play**:
   - Show a Rock, Paper, or Scissors gesture to the camera.
   - The computer will recognize your gesture and move the cardboard hand to display the winning counter gesture.

## Customization

You can modify the game logic to add more cases or gestures by adjusting the hand-tracking conditions in the Python code. More details on how the detection works are provided in the code comments.

## Components List

- Arduino Uno
- Servo Motors (3 or more depending on your hand setup)
- Camera (for gesture detection)
- Python with the following libraries: `serial`, `mediapipe`, `opencv-python`
- Cardboard Hand Replicas (with 3 fingers)

## More Information

For more details on the gesture detection logic or the hardware setup, refer to the code and circuit diagrams provided in this repository.

Feel free to expand the game by adding more gestures or improving the physical hand design.
