# Real_Time_Accident_Detection
This project detects road accidents from CCTV video footage using YOLO object detection and automatically triggers alerts to nearby hospitals based on the location of the camera that recorded the incident.

## 🎯 Features

- Detects `moderate` and `severe` accidents in videos using trained YOLO model
- Maps detected videos to associated CCTV cameras
- Links each CCTV to a real-world location (latitude & longitude)
- Sends alert to the corresponding hospital based on accident location
- Converts output predictions into annotated video and triggers alerts only once per video

---

## 📦 Tech Stack

| Layer            | Tools/Frameworks Used                     |
|------------------|--------------------------------------------|
| Object Detection | [YOLOv11](https://github.com/ultralytics/yolov5) via Roboflow training |
| Coding/Logic     | Python, Google Colab                      |
| File Conversion  | ffmpeg (AVI → MP4)                        |
| Visualization    | Output image/video rendering in Colab     |
| Dataset          | Custom annotated dataset via [Roboflow](https://roboflow.com) |
| Deployment       | GitHub (Jupyter Notebook `.ipynb`)        |

---

## 🚦 How It Works

1. Upload accident videos from CCTV sources
2. Run YOLO prediction (`mode=predict`) with `save_txt=True`
3. Convert YOLO output from `.avi` to `.mp4` using `ffmpeg`
4. Parse saved label `.txt` files and map to:
   - Associated CCTV
   - GPS Coordinates
   - Hospital contact
5. Trigger a one-time alert per video if `moderate` or `severe` class is detected

---

## 📁 Files Included

- `real_time_accident_detection.ipynb` → Core notebook with full pipeline
- `runs/detect/predict/` → YOLO outputs (optional preview images/videos)
- `README.md` → Project overview and instructions
- `output_videos/` → Final .mp4 videos (annotated)

---

## 📸 Sample Output
![accident_reporting](https://github.com/user-attachments/assets/797bd576-4e7b-4e8f-8d41-ffdc572453d3)



## 🏥 Future Enhancements

- Add live CCTV stream input support (e.g., RTSP)
- Real-time hospital alert via email/SMS/Telegram
- Web dashboard with live accident monitoring
- Severity-level based escalation and response time tracking

---
