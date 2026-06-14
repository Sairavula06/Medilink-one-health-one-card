# 🏥 Medilink – One Health One Card

> A unified healthcare management system providing a single digital health card for secure medical record management, doctor-patient interaction, appointment scheduling, e-prescriptions, and AI-assisted disease prediction.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technologies](#technologies)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Running the Application](#running-the-application)
- [Usage](#usage)
- [System Workflow](#system-workflow)
- [AI & Machine Learning](#ai--machine-learning)
- [Database Schema](#database-schema)
- [API Documentation](#api-documentation)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact & Support](#contact--support)

---

## 📖 Overview

Medilink – One Health One Card is a comprehensive healthcare management system designed to provide a centralized platform for patients and doctors. The application enables secure management of medical records, seamless doctor-patient interaction, appointment scheduling, digital prescriptions, and AI-powered disease prediction using advanced machine learning techniques.

**Key Goal:** Digitize healthcare delivery while improving accessibility, security, and the patient-doctor experience.

---

## 🎯 Key Features

### 👥 Patient Module
- ✅ User Registration and Login with secure authentication
- ✅ Search and View Doctor Profiles
- ✅ Book and Manage Appointments
- ✅ Access Personal Medical History
- ✅ View and Download Digital Prescriptions
- ✅ Secure Health Record Management

### 👨‍⚕️ Doctor Module
- ✅ Doctor Registration and Authentication
- ✅ Manage Patient Appointments
- ✅ Generate Digital Prescriptions
- ✅ Access Patient Medical Records
- ✅ AI-Assisted Disease Prediction Support

### 🧠 AI Disease Prediction
- ✅ Brain MRI Analysis using Machine Learning
- ✅ CNN (Convolutional Neural Network) for image-based prediction
- ✅ SVM (Support Vector Machine) for classification
- ✅ Real-time diagnostic assistance for doctors

### 📁 Record Management
- ✅ Centralized Electronic Health Records (EHR)
- ✅ Encrypted storage of patient data
- ✅ Easy retrieval of medical history and prescriptions
- ✅ Audit trail for data access and modifications

---

## 🛠️ Technologies

### Frontend
- HTML5
- CSS3
- JavaScript (ES6+)

### Backend
- Python
- Django Framework
- Django REST Framework (for APIs)

### Database
- MySQL 8.0+

### Machine Learning
- TensorFlow
- Keras
- Scikit-learn
- NumPy
- Pandas
- Matplotlib
- CNN (Convolutional Neural Network)
- SVM (Support Vector Machine)

---

## 📂 Project Structure

```
Medilink-one-health-one-card/
├── frontend/                    # Frontend application
│   ├── static/                 # CSS, JS, images
│   ├── templates/              # HTML templates
│   └── index.html              # Main entry point
├── backend/                     # Django backend
│   ├── medilink/              # Main project settings
│   ├── patients/              # Patient app
│   ├── doctors/               # Doctor app
│   ├── appointments/          # Appointments app
│   ├── prescriptions/         # Prescriptions app
│   ├── ai_prediction/         # ML models
│   └── manage.py              # Django management script
├── ml_models/                  # Machine Learning models
│   ├── cnn_model/             # CNN model for MRI analysis
│   ├── svm_model/             # SVM classifier
│   ├── training_data/         # Training datasets
│   └── trained_models/        # Saved model files
├── database/                   # Database scripts
│   ├── schema.sql             # Database schema
│   └── migrations/            # Django migrations
├── requirements.txt            # Python dependencies
├── .env.example               # Environment variables template
└── README.md                  # This file
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.8+**
- **MySQL 8.0+**
- **pip** (Python package manager)
- **Git**
- **Node.js** (optional, for frontend tooling)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Sairavula06/Medilink-one-health-one-card.git
   cd Medilink-one-health-one-card
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Create the MySQL database:**
   ```bash
   mysql -u root -p < database/schema.sql
   ```

### Configuration

1. **Create a `.env` file** from the template:
   ```bash
   cp .env.example .env
   ```

2. **Update `.env` with your configuration:**
   ```env
   # Database Configuration
   DB_ENGINE=django.db.backends.mysql
   DB_NAME=medilink
   DB_USER=root
   DB_PASSWORD=your_password
   DB_HOST=localhost
   DB_PORT=3306

   # Django Settings
   SECRET_KEY=your_secret_key_here
   DEBUG=False
   ALLOWED_HOSTS=localhost,127.0.0.1

   # Email Configuration (for notifications)
   EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend
   EMAIL_HOST=smtp.gmail.com
   EMAIL_PORT=587
   EMAIL_HOST_USER=your_email@gmail.com
   EMAIL_HOST_PASSWORD=your_email_password

   # ML Model Paths
   CNN_MODEL_PATH=ml_models/trained_models/cnn_model.h5
   SVM_MODEL_PATH=ml_models/trained_models/svm_model.pkl
   ```

### Running the Application

1. **Apply database migrations:**
   ```bash
   cd backend
   python manage.py migrate
   ```

2. **Create a superuser (admin account):**
   ```bash
   python manage.py createsuperuser
   ```

3. **Start the development server:**
   ```bash
   python manage.py runserver
   ```

4. **Access the application:**
   - Frontend: `http://localhost:8000`
   - Admin Panel: `http://localhost:8000/admin`

---

## 💻 Usage

### For Patients
1. Navigate to the registration page and create an account
2. Complete your medical profile
3. Search for doctors by specialty
4. Book an appointment
5. Access your medical history and prescriptions in the dashboard

### For Doctors
1. Register as a doctor with credentials
2. View incoming patient appointments
3. Access patient medical records
4. Generate digital prescriptions
5. Use AI prediction tool to assist with diagnosis (upload MRI scans)

### For Administrators
1. Log in to `/admin`
2. Manage users, doctors, appointments
3. Monitor system activity and records

---

## 🔄 System Workflow

```
┌─────────────────────────────────────────────────────────┐
│ 1. Registration & Authentication                         │
│    - Patients and doctors register and log in            │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 2. Appointment Management                               │
│    - Patients search for doctors                        │
│    - Patients schedule appointments                     │
│    - Doctors view and manage appointments               │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 3. Consultation & Diagnosis                             │
│    - Doctor-patient interaction                         │
│    - Patient medical records accessed                   │
│    - Brain MRI images uploaded (if needed)              │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 4. AI-Powered Analysis                                  │
│    - CNN analyzes MRI images                            │
│    - SVM classifies prediction results                  │
│    - Assists doctor with diagnosis                      │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 5. Prescription & Record Management                     │
│    - Doctor generates digital prescription              │
│    - Medical records updated in database                │
│    - Patient receives prescription notification         │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 6. Patient Access                                       │
│    - Patients view prescriptions and records            │
│    - Download medical documents as PDF                  │
│    - Maintain health history                            │
└─────────────────────────────────────────────────────────┘
```

---

## 🧠 AI & Machine Learning

### CNN (Convolutional Neural Network)
- **Purpose:** Analyze and extract features from brain MRI images
- **Architecture:** Multi-layer convolutional and pooling layers
- **Output:** Probability scores for abnormalities

### SVM (Support Vector Machine)
- **Purpose:** Classify CNN predictions into diagnostic categories
- **Training:** Labeled MRI dataset with known diagnoses
- **Accuracy:** [Insert your model's accuracy percentage]

### Model Performance
- **CNN Accuracy:** [To be filled]
- **SVM F1-Score:** [To be filled]
- **Overall System Recall:** [To be filled]

> **Note:** Models should be retrained quarterly with new data to maintain accuracy.

---

## 🗄️ Database Schema

### Key Tables

**users**
- user_id (PK)
- username, email, password_hash
- first_name, last_name
- user_type (patient/doctor/admin)
- created_at, updated_at

**doctors**
- doctor_id (PK, FK: users)
- specialization, license_number
- experience_years, bio
- contact_number, office_address

**appointments**
- appointment_id (PK)
- patient_id (FK: users)
- doctor_id (FK: doctors)
- appointment_date, status
- reason_for_visit, notes

**prescriptions**
- prescription_id (PK)
- appointment_id (FK: appointments)
- doctor_id (FK: doctors)
- medications, dosage, duration

**medical_records**
- record_id (PK)
- patient_id (FK: users)
- record_type, description
- file_path, created_at

**mri_scans**
- scan_id (PK)
- patient_id (FK: users)
- scan_date, file_path
- cnn_prediction, svm_result

---

## 📡 API Documentation

### Patient Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/patients/register` | Register new patient |
| GET | `/api/patients/<id>` | Get patient profile |
| PUT | `/api/patients/<id>` | Update patient profile |
| GET | `/api/patients/<id>/appointments` | Get patient appointments |
| GET | `/api/patients/<id>/prescriptions` | Get prescriptions |
| GET | `/api/patients/<id>/medical-records` | Get medical records |

### Doctor Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/doctors/register` | Register new doctor |
| GET | `/api/doctors/<id>` | Get doctor profile |
| GET | `/api/doctors/<id>/appointments` | Get doctor's appointments |
| POST | `/api/doctors/<id>/prescriptions` | Create prescription |

### AI Prediction Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/ai/predict-mri` | Upload MRI and get prediction |
| GET | `/api/ai/prediction/<id>` | Get prediction results |

> **Full API documentation available in `/docs/api.md`**

---

## 📋 Objectives

✅ Digitize healthcare record management  
✅ Improve communication between doctors and patients  
✅ Provide AI-powered disease prediction support  
✅ Reduce paperwork and manual record handling  
✅ Enable centralized access to healthcare information  
✅ Ensure data security and patient privacy  

---

## 🔮 Future Enhancements

- 🔐 **Blockchain Integration** – Immutable medical record audit trail
- 📹 **Telemedicine Support** – Video consultation between doctors and patients
- 📱 **Mobile Applications** – Native iOS and Android apps
- 🤖 **Healthcare Chatbot** – AI-powered patient support bot
- 🏥 **Multi-Hospital Integration** – Connect multiple healthcare facilities
- ☁️ **Cloud Synchronization** – Real-time health record sync across devices
- 📊 **Advanced Analytics Dashboard** – Health trends and statistics
- 🔔 **Smart Notifications** – Appointment reminders and health alerts
- 💬 **Prescription Refill System** – Online refill requests
- 🗣️ **Multilingual Support** – Multiple language interfaces

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch:** `git checkout -b feature/your-feature-name`
3. **Commit your changes:** `git commit -m "Add your feature description"`
4. **Push to the branch:** `git push origin feature/your-feature-name`
5. **Open a Pull Request** with a clear description of changes

### Code Standards
- Follow PEP 8 for Python code
- Use meaningful variable and function names
- Write comments for complex logic
- Add unit tests for new features

---


## 🙏 Acknowledgments

- Thanks to the Django and TensorFlow communities
- Medical dataset providers and contributors
- All team members and contributors

---

**⭐ If you find this project helpful, please give it a star!**

---

*Last Updated: June 2025*
