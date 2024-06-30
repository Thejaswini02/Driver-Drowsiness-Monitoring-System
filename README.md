# Driver-Drowsiness-Monitoring-System



*** Components Required  ***

Python Libraries: OpenCV, Dlib, Scipy, Flask

HTML/CSS/JavaScript: For the web interface



Step 1: Setting Up the Environment

Step 2: Drowsiness Detection in Python

Step 3: HTML for Front-End

Step 4: Running the System

a. Place the shape_predictor_68_face_landmarks.dat file in the same directory as your Python script. You can download this file from dlib's model zoo.

b. Run the Flask application:

python drowsiness_detection.py

c. Open a web browser and navigate to http://127.0.0.1:5000/ to see the video feed with drowsiness detection.
This setup creates a basic driver drowsiness monitoring system. You can enhance it further by adding more sophisticated algorithms and features like sending alerts, logging drowsiness events, and integrating with a vehicle's system.



The Driver Drowsiness Monitoring System detailed above combines computer vision techniques with a web interface to detect drowsiness in real-time using a webcam feed. Here is a breakdown of the components and how they work together:

1. Python Backend
Libraries Used:

OpenCV: For capturing video frames and basic image processing.
Dlib: For facial landmark detection.
Scipy: For calculating Euclidean distances, which are essential for computing the Eye Aspect Ratio (EAR).
Flask: For creating a web server to serve the video feed.
Key Components:

Facial Landmark Detection: Using Dlib's pre-trained model to detect 68 facial landmarks, specifically focusing on the eye region.
Eye Aspect Ratio (EAR): A measure to detect whether the eyes are open or closed. If the EAR falls below a certain threshold for a consecutive number of frames, it indicates that the person might be drowsy.
Real-time Video Processing: Capturing frames from the webcam, processing them to detect facial landmarks, and computing the EAR.
Flask Server: Serving the processed video frames as a live video feed to a web interface.



2. HTML Front-End
Components:

HTML Page: A simple web page that displays the video feed from the Flask server.
Video Feed: The live video feed from the webcam, processed by the backend to include drowsiness detection indicators.


How It Works

Video Capture: The system captures video frames from the webcam using OpenCV.
Face Detection: Dlib's frontal face detector identifies faces in the video frames.
Facial Landmark Detection: For each detected face, Dlib's shape predictor identifies 68 facial landmarks.
Eye Aspect Ratio Calculation: EAR is calculated for both eyes. The EAR is the ratio of distances between vertical eye landmarks to the distance between horizontal eye landmarks.
Drowsiness Detection: If the EAR is below a predefined threshold (0.3) for a certain number of consecutive frames (48), a drowsiness alert is triggered.
Web Interface: The Flask server streams the processed video frames to the web interface, displaying the real-time video feed with drowsiness detection alerts.


Customization and Enhancement

Adjust EAR Threshold and Frame Count: Fine-tune the EYE_AR_THRESH and EYE_AR_CONSEC_FRAMES constants to better suit the specific conditions and requirements of your application.
Alert Mechanism: Enhance the alert system to include audio alerts, push notifications, or integration with vehicle systems.
Additional Features: Implement features like logging drowsiness events, analyzing patterns over time, and providing a user dashboard.


Running the System

Setup Environment: Ensure all required libraries are installed.
Prepare Model: Download and place the shape_predictor_68_face_landmarks.dat file in the project directory.
Run Flask Application: Execute the Python script to start the Flask server and begin video processing.
Access Web Interface: Open a web browser and navigate to http://127.0.0.1:5000/ to view the live video feed and monitor drowsiness.

This project provides a foundation for a driver drowsiness monitoring system. It can be further developed and refined to create a robust solution for real-world applications.




The eye region is marked by 6 coordinates. These coordinates can be used to find whether the eye is open or closed if the value of EAR is checked with a certain threshold value.


![image](https://github.com/Thejaswini02/Driver-Drowsiness-Monitoring-System/assets/115609807/4eb5400c-cde8-4643-807b-149aa2dbfd69)






After starting the server, an IP will be displayed on the screen. Open the file android_cam.py. In line 36 put the given IP.

url = "http://<YOUR_IP_HERE>/shot.jpg"
Also, make sure that the phone and PC/Laptop is connected to the same network.

Then, run the system in the same way as mentioned above. Click on the Run Using Phone Cam button to see the results:



![image](https://github.com/Thejaswini02/Driver-Drowsiness-Monitoring-System/assets/115609807/a1904e6e-cbc6-4890-b031-4dad76304983)





Also, we have tried plotting the MAR and EAR graph Vs. Time in order to make the working clearer to the audience. The graph looks like:


![image](https://github.com/Thejaswini02/Driver-Drowsiness-Monitoring-System/assets/115609807/c424aa79-5489-4931-893b-852409ed81f9)





