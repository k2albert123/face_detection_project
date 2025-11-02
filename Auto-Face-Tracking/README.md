# 🎯 Auto Face Tracking System (OpenCV + Arduino)

This project implements an **automatic face tracking system** that uses **OpenCV** for face detection and an **Arduino-controlled stepper motor** to follow the movement of a person’s face in real time.
It simulates an intelligent camera that keeps a speaker’s face centered in the frame as they move.

---

## 🧩 Project Phases

### **Phase 1: Face Detection & Tracking**

* Uses your laptop’s webcam.
* Detects a face using OpenCV.
* Displays a bounding box, movement direction (Left, Right, Up, Down), and estimated speed.

### **Phase 2: Stepper Motor Integration**

* Integrates Arduino Uno with a stepper motor via a motor driver (ULN2003 or A4988).
* Sends serial commands from Python to Arduino.
* Rotates the motor left or right when the detected face moves.

### **Phase 3: Full Auto Face Tracking Camera**

* Mounts a USB camera on the stepper motor.
* The camera physically rotates to keep the face centered — completing the auto-tracking system.

---

## 🖥️ System Requirements

* **Python 3.7+**
* **Arduino IDE**
* **Libraries:**

  * Python: `opencv-python`, `numpy`, `pyserial`
  * Arduino: `Stepper.h`
* **Hardware:**

  * Arduino Uno
  * Stepper Motor (e.g., 28BYJ-48 or NEMA 17)
  * Motor Driver (ULN2003 or A4988)
  * USB Camera
  * Jumper wires, power supply

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/k2albert123/Auto-Face-Tracking.git
cd Auto-Face-Tracking
```

### 2️⃣ Install Python Dependencies

```bash
pip install -r requirements.txt
```

Contents of `requirements.txt`:

```
opencv-python
numpy
pyserial
```

### 3️⃣ Upload Arduino Code

1. Open `motor_control.ino` in Arduino IDE.
2. Select your Arduino board and COM port.
3. Upload the sketch.

### 4️⃣ Run the Python Script

Make sure your Arduino is connected, then run:

```bash
python face_tracking.py
```

* Press `q` to quit the program.

---

## 🧠 Working Principle

1. The **OpenCV script** continuously detects the user’s face and computes its position.
2. When the face moves **left** or **right**, the Python script sends a command (`'L'` or `'R'`) via **Serial** to the Arduino.
3. The **Arduino sketch** receives the command and rotates the stepper motor accordingly.
4. The camera (mounted on the motor) rotates to keep the face centered.

---

## 🔌 Wiring (for 28BYJ-48 + ULN2003 + Arduino Uno)

| ULN2003 Pin | Arduino Pin |
| ----------- | ----------- |
| IN1         | 8           |
| IN2         | 9           |
| IN3         | 10          |
| IN4         | 11          |

---

## 🧾 File Descriptions

| File                | Description                                                     |
| ------------------- | --------------------------------------------------------------- |
| `face_tracking.py`  | Python script handling face detection and serial communication. |
| `motor_control.ino` | Arduino code controlling the stepper motor.                     |
| `requirements.txt`  | List of Python libraries required.                              |
| `README.md`         | Project documentation.                                          |
| `assets/`           | (Optional) Contains setup images, demo GIFs, etc.               |

---

## 📸 Demonstration

You can attach a short GIF or photo of your setup in `/assets/`:

```
assets/setup_photo.jpg
```

---

## 📤 Submission

* Push your project to GitHub:

  ```bash
  git add .
  git commit -m "Auto Face Tracking Project"
  git push -u origin main
  ```

* Submit your **GitHub repository link** via the Google Form provided.

---

## 👨‍💻 Author

**Name:** Kwizera Albert
**Project:** Auto Face Tracking (Y3 Robotics Project)
**Course:** Year 3 Embedded Systems / Computer Vision

---

✨ *“Bringing together Computer Vision and Embedded Systems for intelligent automation.”*
