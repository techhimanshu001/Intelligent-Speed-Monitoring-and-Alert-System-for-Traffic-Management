# Project Description

The **Intelligent Speed Monitoring and Alert System for Traffic Management** is designed to monitor vehicle speeds, detect violations, and automatically recognize vehicle number plates in real-time. The system aims to capture frames when speed violations occur, and email the concerned authority with the captured frame and vehicle number. This project was developed during the **NVIDIA GRIL** training program, which is a comprehensive AI-focused training by NVIDIA. The program empowers developers with hands-on experience in leveraging high-performance computing resources and deep learning frameworks like PyTorch for solving real-world problems. The project uses NVIDIA DGX systems, which are specifically built for accelerated AI computations, making it an ideal platform for this application.

# Project Aim

The goal of this project is to create an intelligent traffic management system capable of:
- Tracking vehicles and detecting their speed.
- Marking violations when a vehicle exceeds the speed threshold.
- Capturing the frame of the vehicle at the time of violation.
- Automatically recognizing the vehicle’s number plate.
- Sending an email to the concerned authority with the captured frame and vehicle number as an attachment.

# Requirements

To set up the project, the following tools and technologies are required:

- **DGX Server:** This powerful server is equipped with high-end NVIDIA GPUs, ideal for processing large volumes of video data and training AI models quickly.<br/>
**Technologies:**<br/>
- **Python 3.8:** Primary language used for backend development and real-time processing.<br/>
- **Flask:** Lightweight web framework for deploying the application as a web service.<br/>
- **PyTorch:** Deep learning framework used for training and deploying the vehicle number plate recognition model.<br/>
- **OpenCV:** Used for real-time video frame processing to detect vehicles and capture frames of violations.<br/>
- **SCP and SSH:** Secure file transfer and remote access tools for managing files and working on the DGX server.<br/>

# Technologies Used

- **Python 3.8:** Python serves as the core programming language for the system, handling video processing, speed detection, violation marking, and number plate recognition.<br/>
- **Flask:** A web framework that makes it easy to deploy the system as a service, where users can monitor violations and receive alerts.<br/>
- **PyTorch:** Used to train the deep learning model for vehicle number plate recognition. PyTorch’s powerful GPU capabilities make it suitable for AI applications.<br/>
- **OpenCV:** This library enables real-time video processing for vehicle tracking, speed detection, and violation capture.<br/>
- **NVIDIA DGX Server:** With powerful GPUs, the DGX system accelerates the training and deployment of AI models, allowing the system to process high-resolution video frames in real-time.<br/>
- **Email System:** Integrated into the system to send automatic violation alerts to the concerned authorities with the captured image and vehicle number.<br/>

# Steps to Setup the Project
1.**Setup DGX Server:** The project utilizes NVIDIA DGX systems for GPU-powered training and model deployment.<br/>
   
- Access the DGX server by navigating to the IP address in your web browser:<br/>
   > http://<DGX_IP_address>:<application_port>
   
- Log in with the required username and password.

2.**Setting Up the Environment (notebook creation):**

   > RAM: 6GB, CPU: 8 cores, GPU: 1 (with 20GB memory), Environment: test<br/>
   > PyTorch Image: Use the appropriate image for PyTorch.<br/>
   > Flask Port: 5000 (default).<br/>

3.**Set up the python virtual environment:**

   >sudo apt update<br/>
   >sudo apt install python3.8-venv<br/>
   >python -m venv newenv<br/>
   >source newenv/bin/activate<br/>

- Install the required dependencies:
   >pip install -r requirements.txt

4.**Transfer Files to DGX Server:** To transfer files from your local machine to the DGX server, use the scp command:

 > scp -r -P <port_number> <local_folder> user@<DGX_IP>:<remote_folder>

5.**Run the System:** After setting up the environment and transferring the necessary files, run the system:

 > python3 app.py

The system will now process live video streams, detect vehicle speeds, mark violations, and trigger email alerts when a violation is detected.

# Annotations and Data Preparation

## Car Annotations
Annotations are a crucial part of the vehicle detection and number plate recognition process. Annotations involve marking the vehicle's position in the image (bounding box) and labeling the object as a vehicle. This annotated data is used to train the model to recognize vehicles and number plates.

To annotate a car:

Draw a bounding box around the vehicle.
Label the car with its class (e.g., "car").
Annotate multiple images to create a diverse dataset for training the model.
The annotated images are then used to train a vehicle detection model that is capable of recognizing and tracking vehicles in real-time.

# Conclusion
This project demonstrates the ability to monitor and manage traffic more efficiently by detecting speed violations and recognizing vehicle number plates automatically. The system leverages the power of NVIDIA’s DGX servers, equipped with GPUs, to accelerate the processing of video feeds and the training of deep learning models. By implementing OpenCV for video frame processing and PyTorch for number plate recognition, this project successfully automates the task of tracking traffic violations, reducing the need for manual monitoring.

From this project, we gained practical experience in building a real-time application for traffic management, using AI to enhance road safety, and leveraging powerful GPU systems for faster model training and deployment.

Thank You for going through my project.
