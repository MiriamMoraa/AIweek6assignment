Edge AI Prototype and Smart Agriculture AI–IoT System
Overview

This repository contains two main components required for the assignment:

Edge AI Prototype

A lightweight image-classification model trained in TensorFlow/Keras.

Conversion to TensorFlow Lite (TFLite) for edge deployment.

Example inference script for Raspberry Pi / simulated Edge device.

Accuracy metrics and deployment explanation.

AI-Driven IoT Agriculture Concept

Proposed smart farming system integrating soil, environmental, and crop sensors.

AI model for predicting crop yield.

Data flow diagram showing how IoT data is processed by the AI model.

Part 1 — Theoretical Analysis
Q1 — How Edge AI Reduces Latency & Enhances Privacy

Edge AI performs inference locally on the device instead of relying on cloud servers.
This eliminates round-trip network delays → low latency, and keeps raw data on-device → enhanced privacy.
Example: Autonomous drones performing object detection onboard to avoid collisions.

Q2 — Quantum AI vs Classical AI

Quantum AI leverages qubits and quantum parallelism to accelerate optimization and search problems.
Industries benefiting most:

Drug discovery

Logistics & route optimization

Finance (portfolio optimization)

Materials science

Part 2 — Practical Implementation
Task 1: Edge AI Image Classification Prototype
1. Training the Model

You train a lightweight CNN using Keras (MobileNetV2 recommended for edge deployment).

Training code is provided in the notebook (edge_ai_model.ipynb).

2. Convert to TensorFlow Lite

You convert the .h5 model to .tflite using:

tflite_model = converter.convert()


(Full script included in convert_and_test.py.)

3. Test TFLite Model

The converted model is evaluated on test images to verify edge performance.

4. Deployment Example (Raspberry Pi)

The repository includes:

pi_infer.py → run inference on Pi camera or local images

Instructions on installing TensorFlow Lite Runtime

5. Benefits of Edge AI for Real-Time Apps

Eliminates cloud delays

Improves privacy

Reduces bandwidth usage

Enables offline functionality

Fits latency-critical domains (drones, robotics, smart traffic systems)

Task 2: AI-Driven IoT Agriculture System
Sensors Needed

Soil moisture sensor

Soil pH sensor

Temperature sensor

Humidity sensor

Light intensity sensor

CO₂ sensor

Camera (crop monitoring)

AI Model for Crop Yield Prediction

Recommended:

Random Forest Regression or

LSTM (if using time-series sensor data)

Data Flow Diagram
[Sensors] → [IoT Gateway] → [Preprocessing] → [AI Model] → [Dashboard/Alerts]

Repository Structure
├── README.md
├── edge_ai_model.ipynb
├── convert_and_test.py
├── pi_infer.py
├── requirements.txt
├── diagrams/
│   └── data_flow_diagram.png
└── model/
    ├── model.h5
    └── model.tflite
