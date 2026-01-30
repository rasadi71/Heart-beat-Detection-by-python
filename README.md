Webcam-Based Heart Rate Detection using rPPG

This project implements a non-contact, real-time heart rate detection system using a standard webcam.
The system estimates heart rate by analyzing subtle color variations on the human face, caused by blood flow, using remote Photoplethysmography (rPPG) techniques.
## this is a repsesentation of a research paper .


📌 Project Overview

Traditional heart rate measurement requires physical contact with sensors.
This project removes that requirement by using:

A webcam for video acquisition

Face detection to locate the region of interest (ROI)

Signal processing techniques to extract heart rate information

The heart rate is calculated in beats per minute (BPM) and displayed in real time.

🧠 Working Principle

The system follows these steps:

Webcam Video Capture
Continuous real-time video frames are captured using OpenCV.

Face Detection
The face is detected using cvzone's FaceDetector to isolate relevant regions.

Forehead ROI Extraction
A region from the forehead is selected, as it provides stable blood flow signals.

Gaussian Pyramid Decomposition
Noise is reduced and subtle color changes are enhanced using Gaussian downsampling.

Green Channel Signal Extraction
The average intensity of the green channel is extracted from each frame, as it is most sensitive to blood volume changes.

Temporal Signal Buffering
Green channel values are stored over time to form a time-domain signal.

Bandpass Filtering (1–2 Hz)
A Butterworth bandpass filter isolates the heart rate frequency range (60–120 BPM).

Signal Amplification
The filtered signal is amplified to highlight subtle pulsations.

Fourier Transform (FFT)
The signal is converted to the frequency domain to identify dominant frequencies.

Heart Rate Calculation
The peak frequency is converted into BPM using:

BPM = 60 × Frequency (Hz)


Real-Time Display
The estimated heart rate is displayed on the video feed.

🛠️ Technologies Used

Python 3

OpenCV

NumPy

SciPy

cvzone

Webcam

📦 Installation

Clone the repository:

git clone https://github.com/your-username/heart-rate-detection-webcam.git
cd heart-rate-detection-webcam


Install required dependencies:

pip install opencv-python numpy scipy cvzone

▶️ How to Run

Run the main script:

python main.py


Controls:

Press Q to quit the application.

📊 Output

Green rectangle shows the forehead ROI

Heart rate is displayed as BPM on the screen

Real-time heart rate estimation

⚠️ Limitations

Sensitive to head movement

Requires stable lighting conditions

Accuracy depends on camera frame rate

Not suitable for medical diagnosis

📚 Applications

Academic research

Signal processing experiments

Computer vision projects

Remote physiological monitoring studies

🔮 Future Improvements

Motion compensation

Multi-face support

Adaptive ROI selection

Machine learning-based heart rate estimation

Mobile camera support

📜 License

This project is released for educational and research use only.

🙌 Acknowledgements

OpenCV community

SciPy & NumPy developers

cvzone library
