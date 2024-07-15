# Intelli_Face_Attendance

Intelli_Face_Attendance is an intelligent facial recognition-based attendance system that uses pre-trained models to detect and recognize faces from images and live video feeds, and records attendance by updating a CSV file.

## Table of Contents

- [Major Functionalities](#major-functionalities)
- [Face Recognition Library](#face-recognition-library)
- [HOG Model](#hog-model)
- [Usage](#usage)
- [Installation](#installation)


## Major Functionalities

### 1. Face Detection and Recognition
- **Face Detection**: The system uses the `face_recognition` library to detect faces in images and video frames. It employs the HOG (Histogram of Oriented Gradients) model to locate faces.
- **Face Recognition**: Once faces are detected, the system encodes them and matches these encodings with the pre-trained encodings of known faces to identify individuals.

### 2. Attendance Management
- **Recording Attendance**: The system records the presence of recognized individuals by updating a CSV file with their names and the current date.
- **Live Video Attendance**: The system can capture real-time video from a webcam, detect and recognize faces, and update attendance records dynamically.

### 3. Data Management
- **Training Data Preparation**: The system processes a dataset of images, encodes the faces, and stores these encodings in a pickle file for quick access during recognition.
- **Validation**: The system can validate its accuracy by comparing recognized faces against a labeled validation set.

### 4. Visualization
- **Display Images**: The system can display images with annotated bounding boxes and names, showing which individuals have been recognized.
- **Live Feed Display**: During live video attendance, the system displays the video feed with real-time annotations of recognized individuals.

## Face Recognition Library

The `face_recognition` library is a simple and powerful library built on top of `dlib`. It provides easy-to-use functions for face detection, face recognition, and manipulation of images. The library is highly efficient and can work with both images and video streams.

### Key Features:
- **Face Detection**: Detects faces within an image using HOG (Histogram of Oriented Gradients) or CNN (Convolutional Neural Network) models.
- **Face Encoding**: Converts faces into a high-dimensional vector representation (encoding) that can be used for comparison.
- **Face Recognition**: Matches a face encoding with a database of known face encodings to recognize the individual.

## HOG Model

The HOG (Histogram of Oriented Gradients) model is used for object detection and has been adapted for face detection in the `face_recognition` library. The HOG method is effective and computationally efficient, making it suitable for real-time applications.

### How HOG Works:
- **Gradient Calculation**: The image is divided into small connected regions called cells, and for each cell, the gradient direction and magnitude are calculated.
- **Histogram Creation**: For each cell, a histogram of gradient directions is created. This histogram represents the distribution of gradient directions within the cell.
- **Normalization**: Histograms are normalized across larger regions of the image, called blocks, to improve accuracy and invariance to lighting changes.
- **Feature Vector**: The normalized histograms are combined to form a feature vector representing the image.

The HOG model is robust to changes in lighting and pose, making it well-suited for detecting faces in varied conditions.

## Usage

### Installation

To use this project, you need to have the following libraries installed:

- `dlib`
- `face_recognition`
- `numpy`
- `opencv-python`
- `pandas`
- `matplotlib`

You can install these dependencies using `pip`:

```sh
pip install dlib face_recognition numpy opencv-python pandas matplotlib
