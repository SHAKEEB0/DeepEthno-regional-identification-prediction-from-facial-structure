<div align="center">
  <h1>🌍 DeepEthno</h1>
  <p><b>Regional Identification Prediction from Facial Structure</b></p>
</div>

> **⚠️ Ethical Disclaimer:** This project demonstrates technical feasibility and is intended strictly for controlled academic research. In real-world applications, extreme caution must be exercised to prevent the misuse of demographic classification systems. Dataset biases, fairness, and privacy preservation are central to the evaluation of this system.

## 📖 About the Project
DeepEthno is a deep-learning-based software framework designed to predict the regional origin of facial images. Leveraging the **YOLOv8 architecture**, the system processes and learns from multi-country facial datasets representing seven distinct regions: **Bhutan, Brazil, Dubai, India, Korea, Nigeria, and South Africa**. 

The platform provides an end-to-end modular workflow for dataset management, model generation, and facial recognition, emphasizing academic reproducibility, real-time performance, and structural feature extraction. 

## 🎯 Problem Statement & Objectives
Traditional facial recognition systems focus on identity verification and often lack the robustness to differentiate faces across diverse global populations. Existing methods struggle with varied ethnic groups due to dataset imbalances and limitations in older architectures.

**DeepEthno aims to:**
* Develop a deep-learning system capable of accurately predicting regional origins from unseen facial inputs.
* Implement a modular Django-based software framework separating dataset management, training, and deployment.
* Ensure academic reproducibility by tracking model metrics, training configurations, and dataset versions.

## 💻 Tech Stack
* **Programming Language:** Python
* **Web Framework:** Django
* **Deep Learning & Computer Vision:** YOLOv8 (Ultralytics), OpenCV
* **Database:** MySQL
* **Frontend:** HTML, CSS, JavaScript (Django Templates)

## ⚙️ Core Modules & Features

### 1. Admin Module
* **Secure Authentication:** Admin login to access backend controls.
* **Dataset Management:** Upload and manage facial datasets categorized by the 7 target countries.
* **Model Generation:** Initiate YOLOv8 model training (`yolov8n.pt`) directly from the uploaded dataset (`data.yaml`).
* **Model Storage:** Save the best training weights for deployment (`best.pt`).

### 2. User Module
* **Registration & Login:** Secure user onboarding and authentication.
* **Image Upload:** Upload unseen facial images for testing.
* **Face Recognition & Inference:** The system loads the trained YOLOv8 model, detects the facial region, runs classification, and predicts the regional category with a confidence score.
* **Visualization:** Displays the uploaded image with bounded boxes and regional labels.

## 🚀 Installation & Setup

**1. Clone the Repository**
```bash
git clone https://github.com/SHAKEEB0/DeepEthno-regional-identification-prediction-from-facial-structure.git
cd DeepEthno-regional-identification-prediction-from-facial-structure
```

**2. Set up a Virtual Environment (Recommended)**
```bash
python -m venv venv
# On Windows use: venv\Scripts\activate
# On Mac/Linux use: source venv/bin/activate
```

**3. Install Dependencies**
Ensure you have the required libraries installed.
```bash
pip install django ultralytics opencv-python pymysql matplotlib
```

**4. Database Configuration**
* Install and start MySQL.
* Create a database named `deepethno`.
* Update your database credentials in `views.py` and `settings.py` (Default: User: `root`, Password: `root`).

**5. Run Migrations & Start the Server**
```bash
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

**6. Access the Application**
Open your browser and navigate to `http://127.0.0.1:8000`.

## 🧠 How the Algorithm Works
1. **Initialization:** The system loads a pre-trained YOLOv8 base model or loads existing custom weights if previously trained.
2. **Training:** YOLOv8 is trained on the custom dataset of labeled faces from 7 countries to learn unique structural patterns.
3. **Inference:** When a user uploads an image, the model performs detection to isolate the face region (filtering out background noise).
4. **Classification:** The model extracts features, classifies the regional origin, and visualizes the results by drawing bounding boxes with the predicted country label.

## 📈 Non-Functional Requirements Addressed
* **Performance:** Inference responds in under 3 seconds per image.
* **Maintainability:** Clear modular separation between core recognition logic and UI.
* **Privacy:** Uploaded images are strictly managed, reinforcing ethical system design.

## 🔮 Future Scope
Future iterations of DeepEthno will focus on expanding datasets to include more countries and ethnicities to further mitigate bias. Advancements may include integrating Explainable AI (XAI) to interpret which facial features drive classification, optimizing the model for edge devices using TensorRT or ONNX, and incorporating multimodal contextual data to enhance robustness.

---
*Developed as an academic prototype for computer vision and fairness-aware AI research.*
