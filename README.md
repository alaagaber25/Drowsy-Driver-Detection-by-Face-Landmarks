# Drowsiness Detection System
## Description
This project is a real-time **Drowsiness Detection System** using Python and OpenCV. It tracks eye movements through a webcam, calculates the **Eye Aspect Ratio (EAR)**, and triggers an alarm if drowsiness is detected. Ideal for **driver safety and fatigue detection**, it provides visual alerts and sound warnings to help prevent accidents.
---
## Drowsiness Detection Method Overview

This project implements a drowsiness detection system that relies on monitoring the **Eye Aspect Ratio (EAR)**—a simple yet effective metric to determine whether a person’s eyes are open or closed.

### Key Concepts

- **Facial Landmark Detection:**  
  The system utilizes a pre-trained facial landmark predictor to locate key points on a person’s face. These points, especially those outlining the eyes, are critical for subsequent analysis.

- **Calculating the Eye Aspect Ratio (EAR):**  
  The EAR is computed by comparing the vertical distances (between the eyelid landmarks) to the horizontal distance (between the corners of the eyes). When the eyes are open, the vertical distances are relatively large compared to the horizontal distance. When the eyes begin to close, these vertical distances decrease, causing the EAR to drop.

- **Determining Drowsiness:**  
  By monitoring the EAR over consecutive frames in a video stream, the system can detect when the eyes remain closed for an extended period. A consistently low EAR signals that the individual might be drowsy, at which point an alarm is activated to prompt alertness.

This approach, based on real-time computer vision techniques, offers a reliable and efficient way to monitor and address drowsiness, especially in applications like driver alertness systems.

![EAR Calculation](https://learnopencv.com/wp-content/uploads/2022/09/03-driver-drowsiness-detection-EAR-points.png)

---

## Features

- **Real-time Video Processing:** Uses the webcam to capture live video.
- **Facial Landmark Detection:** Utilizes dlib’s pre-trained shape predictor to detect facial landmarks.
- **Eye Aspect Ratio (EAR) Calculation:** Computes EAR to determine if the eyes are closed.
- **Drowsiness Alert:** Plays an alarm sound if drowsiness is detected over consecutive frames.
- **Visual Feedback:** Displays the live video with eye contours and drowsiness warnings.

---

## Requirements

- Python 3.x
- [OpenCV](https://opencv.org/) (`cv2`)
- [dlib](http://dlib.net/)
- [imutils](https://github.com/jrosebr1/imutils)
- [scipy](https://www.scipy.org/)
- [pygame](https://www.pygame.org/)
- A pre-trained facial landmark detector file: `shape_predictor_68_face_landmarks.dat`
---

## Code Structure

- **Imports and Global Variables:**  
  All required libraries and paths (for the model and alarm) are defined at the beginning.

- **Utility Function (`eye_aspect_ratio`):**  
  Calculates the EAR based on the distances between specific eye landmarks.

- **Main Code Flow:**  
  - Initializes the webcam and processes video frames.
  - Detects faces and computes the EAR.
  - Displays visual cues (eye contours and warnings) and triggers the alarm if drowsiness is detected.
  - Contains a loop that terminates when the user presses "q".


