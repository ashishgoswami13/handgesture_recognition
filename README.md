# Hand Gesture Recognition

This project enables real-time hand gesture recognition using computer vision and deep learning. It is designed to collect gesture data, train a model, and perform live gesture classification, which can be used for applications such as drone control or human-computer interaction.

## Folder Structure & File Explanations

### data_collection
- **datacollection.py**
  - Used to collect hand gesture images from a webcam.
  - Saves images into gesture-specific folders (e.g., `back/`, `down/`, etc.) for dataset creation.
  - Helps build a labeled dataset for training the recognition model.

- **test.py**
  - Loads the trained model from the `Model/` folder.
  - Uses the webcam to detect and classify hand gestures in real-time.
  - Detects a hand, preprocesses the image, and predicts the gesture using the trained model.

- **Gesture Folders** (`back/`, `down/`, `Go forward/`, `land/`, `left/`, `right/`, `stop/`, `up/`)
  - Contain images of hands showing different gestures.
  - Used for training and testing the recognition model.

### Model/
- **keras_model.h5**
  - The trained Keras model for hand gesture recognition.
  - Used by `test.py` to classify gestures.

- **labels.txt**
  - Contains the list of gesture labels corresponding to the model’s output classes.
  - Used to map model predictions to human-readable gesture names.

## How It Works
1. **Data Collection**: Run `datacollection.py` to capture images of different hand gestures and save them in the respective folders.
2. **Model Training**: (Not included here, but typically you would train a model using the collected images and save it as `keras_model.h5`.)
3. **Gesture Recognition**: Run `test.py` to use your webcam for live gesture recognition using the trained model.

## Requirements
- Python 3.x
- OpenCV (`cv2`)
- cvzone
- numpy
- Keras

## Usage
1. Install dependencies:
   ```bash
   pip install opencv-python cvzone numpy keras
   ```
2. Collect gesture images:
   ```bash
   python data_collection/datacollection.py
   ```
3. Upload samples of each gesture class (from each folder) as separate classes on [Google Teachable Machine](https://teachablemachine.withgoogle.com/). Train your model and export it as `keras_model.h5` and `labels.txt`, then place them in the `Model/` folder.

4. Run real-time recognition:
   ```bash
   python data_collection/test.py
   ```

--- 

## Author
- ashishgoswami2121@gmail.com
