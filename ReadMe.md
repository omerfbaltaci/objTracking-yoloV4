# objTracking-yoloV4

## Project Description
This project implements a vehicle tracking system using YOLOv4 for object detection and a custom tracking algorithm. It processes video input to detect and track vehicles, assigning unique IDs to each detected vehicle and visualizing their movements in real-time.

## Features
- Object detection using YOLOv4
- Vehicle tracking with unique ID assignment
- Real-time visualization of tracked vehicles
- Euclidean distance-based tracking algorithm
- Processing of video input
- GPU acceleration support using CUDA

## Project Structure
- `ObjectTracking.py`: Main script for vehicle tracking
- `ObjectDetection.py`: Contains the ObjectDetection class for YOLOv4 implementation
- `dnn_model/`: Directory containing YOLOv4 weights, configuration, and class names

## Prerequisites
- Python 3.x
- OpenCV (cv2)
- NumPy
- CUDA-capable GPU (for GPU acceleration)

## Installation
1. Clone the repository:
   ```
   git clone https://github.com/omerfbaltaci/objTracking-yoloV4.git
   cd objTracking-yoloV4
   ```
2. Install the required packages:
   ```
   pip install opencv-python numpy
   ```

Note: The necessary YOLOv4 weights, configuration files, and class names are already included in the repository.

## Usage
1. Place your input video file (named `highway2.mp4`) in the project directory.
2. Run the main script:
   ```
   python ObjectTracking.py
   ```
3. The processed video will be displayed, showing tracked vehicles with their IDs.
4. Press 'q' to exit the program.

## How It Works

### ObjectDetection.py
- Initializes the YOLOv4 model using OpenCV's DNN module
- Configures the model for GPU acceleration using CUDA
- Provides methods for loading class names and performing object detection

### ObjectTracking.py
1. Initializes the ObjectDetection class and video capture
2. For each frame:
   - Performs object detection using YOLOv4
   - Calculates center points of detected objects
   - Implements a tracking algorithm based on Euclidean distance
   - Assigns and maintains unique IDs for tracked vehicles
   - Visualizes tracked vehicles with circles and ID labels
3. Displays the processed frame and updates tracking information

## Configuration
- Adjust `nmsThreshold` and `confThreshold` in `ObjectDetection.py` to fine-tune detection sensitivity
- Modify the distance threshold (currently 20 pixels) in `ObjectTracking.py` to adjust tracking sensitivity

## Contributing
Contributions to improve the project are welcome. Please follow these steps:
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments
- YOLOv4 for object detection
- OpenCV community for computer vision tools and DNN module
