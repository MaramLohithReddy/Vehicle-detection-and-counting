# Vehicle-detection-and-counting

This project performs **real-time vehicle detection and directional counting** (UP/DOWN) using the [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) object detection framework. It is optimized to process only the first 10 seconds of video input, which is ideal for testing and evaluation purposes in limited compute environments such as Google Colab.

## 🎯 Objective

- Detect and classify vehicles (Car, Motorcycle, Bus, Truck) in video frames.
- Track their movement direction relative to a fixed horizontal line.
- Count the number of vehicles crossing the line in UP and DOWN directions.
- Display overall counts as well as class-wise directional counts on the video output.

## 🧩 Components Used

- **YOLOv8 (Ultralytics)**: Lightweight neural network model for object detection.
- **OpenCV**: For video frame processing, drawing annotations, and video I/O.
- **NumPy**: Efficient array operations.
- **defaultdict (collections module)**: For managing class-wise count tracking.

## 📁 Directory Structure
/Main/
│
├── 56310-479197605_small.mp4 # Input video file
├── output_with_count.mp4 # Output video with overlays
├── vehicle_counting.py # Python script (optional export)
└── README.md # This file

## ⚙️ How It Works

1. **Model Loading**: YOLOv8n is loaded via `ultralytics`.
2. **Frame Processing**: Each frame is processed up to 10 seconds (based on FPS).
3. **Detection & Filtering**: Only COCO vehicle class IDs (2, 3, 5, 7) are considered.
4. **Object Tracking**: Objects are tracked using a basic centroid-based tracking method.
5. **Direction Inference**:
   - If the centroid moves **downward** across the reference line (`line_y`): `DOWN` count is incremented.
   - If it moves **upward**: `UP` count is incremented.
6. **Class-wise Count Maintenance**: Counts are maintained separately for each vehicle class and direction.
7. **Visualization**: Bounding boxes, centroids, direction lines, and counters are overlaid on video.

## output snapshot

<img width="1276" height="691" alt="image" src="https://github.com/user-attachments/assets/6830e423-35d5-4c36-861c-cab7009bd1fe" />



