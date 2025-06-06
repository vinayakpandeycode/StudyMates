StudyMates - Intelligent Peer Collaboration for Academic Success
A platform that helps you find the right study partners.
🚀 Project Description
StudyMates is a web-based application specifically designed to help university students form effective study groups. It connects students based on their academic year, subjects or specialization, and desired group size. A secure ID verification process is also included to ensure authentic student participation.

✨ Key Features
Student Registration: Students can easily register with their name, email, academic year, subjects/specialization, desired group size, and WhatsApp contact.

Secure Student ID Verification: Users upload an image of their student ID card. Our system uses advanced OCR (Optical Character Recognition) technology to verify the student's identity against their registered details.

Intelligent Peer Matching: Based on registration data (year, subjects/specialization, group size), the system intelligently identifies and suggests compatible study partners.

Dynamic Study Room: A dedicated space where users can see their status and view details of their matched study partners.

Conditional Contact Reveal: For privacy and security, the WhatsApp contact details of matched partners are only revealed when both parties have successfully completed their ID verification.

Clean and Intuitive UI: A user-friendly interface for easy navigation and interaction.

💻 Technologies Used (Technology Stack)
This project uses a hybrid architecture that combines the efficiency of Python for web development with the power of Java for critical processing.

Frontend (User Interface):

HTML: For structuring all web pages (registration, thank you, study room).

CSS: For modern styling and responsive design across all devices.

JavaScript: For client-side interactivity, form validation, and AJAX calls for dynamic updates (e.g., ID verification status).

Backend (Core Logic & API):

Python (Flask Framework): The central nervous system of the application. It handles:

API routing and request handling.

User registration and session management.

Secure file uploads (ID cards).

Orchestrating the call to the external ID verification service.

Implementing the core study partner matching logic.

Providing HTML templates and JSON API responses to the frontend.

Pillow (Python Imaging Library): Used for efficient pre-processing of uploaded ID card images (e.g., format conversion) before they are sent for OCR.

ID Verification Service (Specialized Microservice):

Java: Chosen for its robustness, performance, and maturity in handling complex, computationally intensive tasks.

Apache Maven: Manages dependencies and builds the executable Java JAR file for the OCR service.

Tesseract OCR (via Tess4J): The industry-standard open-source OCR engine. Integrated via Tess4J, it precisely extracts textual data (like name, enrollment number) from student ID card images.

Gson (Java JSON Library): Facilitates seamless and efficient JSON data exchange between the Java OCR service and the Python Flask backend.

🛠️ Setup and Run
Follow these steps to run the project locally:

Clone the Repository:

git clone <your-repository-URL>
cd StudyMates

Create Folder Structure: Ensure you have this structure:

StudyMates/
├── app.py
├── pom.xml
├── requirements.txt
├── sample_id.txt
├── users.json
├── templates/
│   ├── index.html
│   ├── thankyou.html
│   └── room.html
├── src/
│   └── main/
│       └── java/
│           └── com/
│               └── studygroup/
│                   └── verification/
│                       └── PythonIDVerifier.java
├── target/         # Will be created by Maven
└── tessdata/       # For Tesseract language data

Install Python Dependencies:

pip install -r requirements.txt
pip install Pillow

Install Java and Maven:

Ensure JDK 17+ and Apache Maven are installed on your system.

Download Tesseract Language Data:

Download the eng.traineddata file from https://github.com/tesseract-ocr/tessdata_fast.

Place this file in your StudyMates/tessdata/ folder.

Build the Java JAR:

Navigate to the StudyMates/ directory (where pom.xml is).

Run this command:

mvn clean install

This will create the target/frontend-1.0-SNAPSHOT-jar-with-dependencies.jar file.

Run the Flask Application:

From the StudyMates/ directory, run:

python app.py

Visit http://127.0.0.1:5000/ in your browser.

💡 Future Enhancements & Scope
Persistent Data Storage: Implement a real database like PostgreSQL or MongoDB for user data.

Real-time Communication: Integrate WebSockets (e.g., Flask-SocketIO) for live updates in study groups and in-app chat functionality.

Advanced Matching Algorithms: Include more granular criteria like availability, preferred study methods, and specific academic goals.

User Profiles & Reviews: Allow users to create detailed profiles and provide feedback on study partners.

Admin Dashboard: A dedicated interface for university administrators to manage users and monitor platform activity.

Scalable Deployment: Prepare for cloud deployment using Docker containers and cloud platforms (AWS, Google Cloud, Heroku).

🤝 Contributing
To contribute, please open an issue or submit a pull request.

📄 License
This project is licensed under the MIT License. See the LICENSE file for more details.
