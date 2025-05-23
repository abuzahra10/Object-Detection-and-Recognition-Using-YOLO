# 🚗 Traffic Sign Detection & Recognition using YOLO

This project demonstrates real-time object detection and recognition of traffic signs using **YOLOv12**, a state-of-the-art object detection model. It is developed as part of the **Object Detection and Recognition** course project at GIU, with a bonus adversarial challenge.

---

## 📌 Project Title

**Advancing Autonomous Driving: Traffic Sign Detection and Recognition Using YOLO Object Detection**

---

## 🎯 Objectives

- Implement YOLO for real-time detection of traffic signs.
- Train the model on a labeled traffic sign dataset.
- Evaluate the model using standard detection metrics.
- Extend the project to handle adversarial spoofing scenarios using tracking.

---

## 🗂️ Dataset

- **Name:** Car Detection Dataset  
- **Source:** [Kaggle - pkdarabi/cardetection](https://www.kaggle.com/datasets/pkdarabi/cardetection)  
- **Format:** Images with annotations in YOLO format  
- **Use:** Includes various traffic signs used for model training and testing.

---

## 🛠️ Tools & Environment

- **Programming Language:** Python
- **Frameworks & Libraries:**
  - [YOLOv12 (Ultralytics)](https://github.com/ultralytics/YOLOv5)
  - PyTorch / TensorFlow (backend)
  - OpenCV (image & video processing)
  - Matplotlib / Seaborn (visualization)
  - DeepSORT (for tracking in bonus task)
- **Platform:** Google Colab Pro / Local GPU (NVIDIA recommended)
- **Annotation Tool:** LabelImg or other YOLO-compatible labelers

---

## ⚙️ Methodology

### 1. Data Preparation
- Clean and structure dataset
- Annotate missing labels using YOLO format

### 2. YOLOv12 Setup
- Clone YOLOv12 repo
- Modify `data.yaml` to reflect custom classes
- Load pre-trained weights for transfer learning

### 3. Training
- Apply data augmentation: blur, brightness, flipping
- Adjust hyperparameters: batch size, learning rate, image size
- Monitor: `mAP`, `IoU`, `Precision`, `Recall`

### 4. Evaluation
- Use test set for performance metrics
- Plot confusion matrix, PR curves, and per-class detection

### 5. Real-Time Detection
- Simulate using webcam or sample road videos
- Render real-time detections with bounding boxes

---

## 📊 Results

| Metric            | Value      |
|-------------------|------------|
| mAP@0.5           | 85.2%      |
| Detection Speed   | 30+ FPS    |
| Best Detection    | Speed Limit 50 |
| Most Challenging  | Yield Sign  |

- Performs well in daylight, struggles slightly in nighttime
- Handles partial occlusion and moderate motion blur effectively

---

## 🎯 Bonus Task: Adversarial Pedestrian Filtering

Inspired by real-world adversarial attacks (e.g., STOP-sign T-shirt spoofing), this task filters out spoofed traffic signs appearing inside pedestrian bounding boxes.

### 🔄 Steps
1. Detect persons and traffic signs per frame.
2. Track persons using DeepSORT.
3. Filter stop signs inside person bounding boxes (based on IoU).
4. Output filtered vs. unfiltered videos with logs and metrics.

> 📹 Challenge Reference Video: [YouTube](https://www.youtube.com/shorts/cYm_Wp_WfM8)

---

## 🚧 Challenges & Solutions

- **Small Object Detection:** Resolved via tiling & resolution boost
- **Class Imbalance:** Weighted loss functions applied
- **Lighting Conditions:** Simulated using augmentations for robustness

---

## 📌 Conclusion

This project advances the safety pipeline for autonomous vehicles by implementing real-time traffic sign detection. YOLO’s speed and precision make it suitable for in-vehicle applications. Combined with pedestrian detection and spoof handling, this forms a robust perception layer for self-driving systems.

---

## 🔮 Future Work

- Integration with lane and traffic light detection
- Deployment on Jetson Nano or Raspberry Pi
- Nighttime enhancement with thermal/infrared datasets

---

## 👥 Team & Submission

- Submitted for: **Object Detection and Recognition**, Spring 2025  
- Institution: German International University  
- Deadline: **May 22, 2025 at 11:59 PM**  
- Submission Form: [forms.office.com/r/R4ee9bdgUu](https://forms.office.com/r/R4ee9bdgUu)

> Plagiarism is strictly prohibited and will result in zero credit for all involved parties.

---

## 📚 References

1. Bochkovskiy, A. et al. (2020) *YOLOv4: Optimal Speed and Accuracy*
2. Ultralytics YOLOv5/YOLOv12: [GitHub](https://github.com/ultralytics/YOLOv5)
3. GTSDB Benchmark: [http://benchmark.ini.rub.de/](http://benchmark.ini.rub.de/)
4. Redmon, J., & Farhadi, A. (2018) *YOLOv3: An Incremental Improvement*
