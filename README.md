# Eye-Blink-Detection
This Python script is designed for real-time blink detection using facial landmarks. It utilizes the dlib library for facial landmark detection and OpenCV for video stream processing. Below is an overview of the key components and functionality of the code:

# Eye Aspect Ratio (EAR)

The script calculates the Eye Aspect Ratio (EAR) for each frame. EAR is a measure of how open or closed a person's eyes are and is used to detect blinks. It's computed as the ratio of the distances between certain landmarks on the eyes. When the EAR falls below a predefined threshold, it indicates a blink.
The EAR is caclualted using the following formula where the numerator of this equation computes the distance between the vertical eye landmarks while the denominator computes the distance between horizontal eye landmarks, weighting the denominator appropriately since there is only one set of horizontal points but two sets of vertical points.
![git4](https://github.com/nourhenehanana/Eye-Blink-Detection/assets/93352403/4a54baad-e6a1-44f5-bbe5-b73f9b72c851)
![git5](https://github.com/nourhenehanana/Eye-Blink-Detection/assets/93352403/73c4710a-5296-440b-86ef-1db3e7e65a21)


# Face Detection and Landmark Prediction
The code employs dlib's face detector to locate faces in each frame. Once a face is detected, the facial landmark predictor is used to determine the positions of specific facial landmarks, including those of the eyes.

# Blink Detection
For each frame, the EAR is calculated for both eyes, and the script keeps track of the number of consecutive frames where the EAR is below the blink threshold. When the eyes are closed for a sufficient number of consecutive frames, it is counted as a blink.

# Visualization
The script visualizes the eyes and their corresponding convex hulls (the outline of the eyes) on the video frame. Additionally, it displays the total number of blinks detected and the computed EAR on the frame.

# Dependencies
To run this code, you'll need the following Python libraries and packages:
You should download "shape_predictor_68_face_landmarks"
dlib
OpenCV (cv2)
NumPy
