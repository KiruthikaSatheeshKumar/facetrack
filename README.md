
---

# FACETRACK – Face Recognition Attendance System with Anti-Spoofing & Admin Panel

FACETRACK is a smart, real-time face recognition-based attendance system built using **Python**, **Streamlit**, **OpenCV**, and **dlib**. It includes an admin dashboard, face registration, live tracking, anti-spoofing measures, and detailed attendance logging.

> **Login:**
> `Username: admin`
> `Password: abc12345`

---

## 🚀 Features

* 🎥 Real-time face detection and recognition using webcam
* 🧠 Face encoding and matching with pre-trained models
* 🙅‍♀️ Anti-spoofing using 68-point facial landmarks
* 🧾 Auto-generated CSV attendance with timestamps
* 🧑‍💼 Admin login & dashboard to monitor records
* 📄 Streamlit-based UI for a seamless user experience
* 📸 Image dataset stored locally and converted to embeddings

---

## 🗂️ Project Structure

```
FACETRACK/
├── Tracking.py                   # Main recognition/tracking script
├── config.yaml                  # Config for dataset/model paths
├── admin_config.yaml            # Admin credentials/config
├── requirements.txt             # Python dependencies
├── dataset/                     # Images of known persons + encoded .pkl file
│   ├── 1_Elon_Musk.jpg
│   ├── ...
│   └── database.pkl
├── register/attendance.csv      # Auto-updated attendance logs
├── assets/                      # UI elements (images, gifs)
├── pages/                       # Streamlit multi-page interface
│   ├── 0_🔒_Admin.py
│   └── ...
├── admin/                       # Admin authentication/dashboard
│   ├── admin_auth.py
│   └── admin_dashboard.py
├── anti_spoof/                  # Anti-spoofing logic
│   ├── anti_spoof.py
│   └── shape_predictor_68_face_landmarks.dat
├── templates/                   # HTML template for report generation
└── utils.py                     # Shared utility functions
```

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/FACETRACK.git
cd FACETRACK
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate       # Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

> If `dlib` fails to install:

* **Windows**: `pip install cmake`
* **Linux**: `sudo apt install build-essential cmake`

---

## ▶️ Running the App

```bash
streamlit run Tracking.py
```

### Use the sidebar to navigate:

* Admin Login
* Face Registration
* Live Face Tracking
* View Attendance Data

---

## 👤 How to Add New Faces

1. Add a **clear frontal image** to `dataset/` in the format:

   ```
   [ID]_[Full_Name].jpg
   ```

   Example:

   ```
   4_Tony_Stark.jpg
   ```

2. Go to the **Register** page in the UI and click **Register Face** to encode and store the new face.

---

## 📋 Attendance Logs

* Logged into `register/attendance.csv`
* Each entry includes:

  * Full Name
  * Date
  * Time

---

## 🔐 Admin Panel

* Navigate to **Admin Login** in the sidebar
* Default credentials are in `admin_config.yaml`
* Features:

  * View registered users
  * Monitor attendance logs
  * Access admin-only settings

---

## 🧠 Anti-Spoofing

To prevent spoofing (e.g., using a photo), the system includes:

* **dlib’s 68-point facial landmarks** for structural validation
* **Real-time geometry checks** to confirm live human features before logging attendance

---

## 📄 Dependencies

Install all dependencies with:

```bash
pip install -r requirements.txt
```

### Key Python Packages:

* `face_recognition`
* `opencv-python`
* `dlib`
* `streamlit`
* `numpy`
* `pyyaml`
* `pandas`

---

## 🙏 Credits

* Anti-spoofing uses dlib’s 68-point shape predictor, trained by **Davis King**
* Inspired by **DATCT's Face Recognition Attendance System**
* Thanks to the **open-source community** for contributions and model availability

---

## 📜 License

This project is licensed under the **MIT License**.
You’re free to use, modify, and distribute — just give proper credit to the original authors and referenced repositories.

---

