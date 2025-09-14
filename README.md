# 🏀 Real-time-Basketball-Violation-Detection

## 🎯 Purpose
Basketball is one of the most dynamic sports, but also one of the most criticized for referee decisions that can change the outcome of championships.  
While other sports like **Tennis** (ball tracking) and **Track & Field** (finish line detection) have embraced computer vision, basketball has lagged behind.

The **AI Basketball Referee** project aims to bring fairness and data-driven analysis to basketball by:
- Detecting **travels** and **double dribbles** in real time.  
- Supporting referees with instant decision feedback.  
- Collecting valuable gameplay data for **machine learning models** and **sports analytics**.

---

## ⚙️ How It Works
The system combines **YOLO object detection** and **pose estimation** to track both the basketball and players’ body movements.

1. **Basketball Detection**  
   - A custom-trained YOLO model (trained on **3,000 annotated images**) detects basketballs in real time.  
   - Handles diverse poses, lighting, and backgrounds.  
   - Outputs bounding boxes for detected basketballs.

2. **Pose Estimation**  
   - Uses YOLO pose estimation to track keypoints (ankles, knees, hips, elbows, wrists).  
   - Enables analysis of player movement and interaction with the ball.

3. **Travel Detection**  
   - Analyzes player movement across frames.  
   - Detects when a player takes steps without dribbling or exceeds allowed movement.  

4. **Double Dribble Detection**  
   - Monitors ball-hand interactions.  
   - Detects if a player dribbles, stops, then dribbles again without passing or opponent interference.  

5. **Real-Time Feedback**  
   - Highlights violations directly on the video feed.  
   - Generates logs/alerts for post-game review or coaching analysis.  

---

## 🛠️ Setup

1. **Clone the repository**  
   ```bash
   git clone <your-repo-url>
   cd AI-Basketball-Referee
   ```

2. **Create a conda environment**  
   ```bash
   conda create -n exercise-tracking python=3.11
   conda activate exercise-tracking
   ```

3. **Install dependencies**  
   ```bash
   pip install ultralytics
   ```

4. **Run the referee scripts**  
   ```bash
   python double_dribble.py
   python travel_detection.py
   ```

5. **Choose your input source**  
   - Webcam:
     ```python
     cv2.VideoCapture(0)
     ```
   - Video file:
     ```python
     cv2.VideoCapture("video.mp4")
     ```

---

## 📂 Model File (`basketballModel.pt`)
The trained basketball detection model is too large for GitHub.  
Please download it here and place it in your project directory:  

👉 [Download basketballModel.pt](https://drive.google.com/file/d/1e6HLRuhh1IEmxOFaxHQMxfRqhzD92t3B/view?usp=sharing)

---

## 🔮 Customizability & Expansion
- Adjustable thresholds for detection sensitivity.  
- Expandable to detect **additional violations** (e.g., fouls, out-of-bounds).  
- Potential for integration into **coaching tools** or **live referee assistance**.  

---

## 🚀 Summary
The **AI Basketball Referee v2.0** leverages **YOLO + pose estimation** to detect:
- ✅ Travels  
- ✅ Double Dribbles  

It provides **real-time visual feedback** and is fully extensible for future rule detection, making basketball fairer, smarter, and more data-driven.
