# Rock, Paper, Scissors Game with YOLO Object Detection

This project implements a real-time Rock, Paper, Scissors game using a webcam and YOLO object detection to recognize hand gestures. The game is designed to track gestures for two players and determine the winner based on the classic Rock, Paper, Scissors rules.

## Features

- Real-time gesture detection using YOLO model
- Tracks gestures for two players
- Displays scores for both players
- Determines the winner based on Rock, Paper, Scissors rules

## Requirements

- Python 3.9
- OpenCV
- NumPy
- Ultralytics YOLO

## Installation

1. **Clone the repository**
    ```bash
    https://github.com/AmmarMohamed0/Vision-RPS-Game.git
    cd Vision-RPS-Game
    ```

2. **Install the required packages**
    ```bash
    pip install opencv-python-headless numpy ultralytics
    ```

3. **Download the YOLO model weights**
    - Ensure you have the `best.pt` weights file in your project directory. If you don't have it, you'll need to train your YOLO model or obtain the weights from a reliable source.

## Usage


   **Play the game**
    - Ensure your webcam is properly connected.
    - Place your hand gestures within the webcam's view.
    - The game will detect gestures for two players and update the scores based on the rules of Rock, Paper, Scissors.
    - The scores and the current game state will be displayed on the screen.


## Code Overview

The game is implemented in `RPS Game.ipynb`. Here's a brief overview of the main components:

- **Initialization**: 
    ```python
    model = YOLO("best.pt")
    cap = cv2.VideoCapture(0)
    All_Classes = ['Paper', 'Rock', 'Scissors']
    Player1_Score = 0
    Player2_Score = 0
    Last_update_time = time.time()
    update_interval = 5
    ```

- **Main Loop**: 
    - Captures frames from the webcam.
    - Uses YOLO model to detect hand gestures.
    - Determines the gestures for Player 1 and Player 2.
    - Updates scores based on the detected gestures and displays them.
    - Shows the processed frame with detected gestures and scores.

- **Determine Winner**: 
    ```python
    def determine_winner(gesture1, gesture2):
        if gesture1 == gesture2:
            return 0
        elif (gesture1 == 'Rock' and gesture2 == 'Scissors') or \
             (gesture1 == 'Scissors' and gesture2 == 'Paper') or \
             (gesture1 == 'Paper' and gesture2 == 'Rock'):
            return 1
        else:
            return 2
    ```

## Acknowledgements

- This project uses the Ultralytics YOLO model for object detection.
- OpenCV for image processing and video capture.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

