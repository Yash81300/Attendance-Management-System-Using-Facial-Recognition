# Face Recognition Attendance System

A real-time attendance management system using face recognition with anti-spoofing detection to prevent fraud attempts.

## Features

- **Real-time Face Recognition**: Instant user identification via webcam
- **Anti-Spoofing Protection**: Detects and blocks photo/video-based fraud attempts
- **Automated Attendance Logging**: Timestamped CSV records for login/logout
- **User Management**: Easy registration system with face encoding storage
- **Live Preview**: 640x480 webcam feed with intuitive GUI

## Tech Stack

- **Python 3.11**
- **OpenCV**: Real-time video processing
- **face_recognition**: 128-dimensional face embeddings
- **Tkinter**: GUI interface
- **PyTorch**: Deep learning inference
- **Minivision Silent-Face-Anti-Spoofing**: Pre-trained liveness detection models

## Anti-Spoofing Detection

This project integrates the [Silent-Face-Anti-Spoofing](https://github.com/minivision-ai/Silent-Face-Anti-Spoofing) library by Minivision for liveness detection:
- **Models**: MiniFASNetV1SE and MiniFASNetV2
- **Purpose**: Prevent unauthorized access via printed photos or video replays
- **Confidence Threshold**: 60% for real face classification

The `src/` directory and pre-trained model weights (`.pth` files) are from their open-source repository.

## Installation
```bash
# Clone the repository
git clone https://github.com/Yash81300/face-recognition-attendance.git
cd face-recognition-attendance

# Install dependencies
pip install -r requirements.txt
```

## Usage
```bash
python main.py
```

1. Click **Register** to add new users
2. Click **Login** to mark attendance (in)
3. Click **Logout** to mark attendance (out)

Attendance records are saved in `log.txt`.

## Project Structure
```
├── main.py                 # Main application
├── util.py                 # Helper functions for recognition
├── test.py                 # Anti-spoofing test interface
├── db/                     # User face encodings (gitignored)
├── resources/              # Pre-trained models
│   ├── anti_spoof_models/  # Minivision liveness detection
│   └── detection_model/    # RetinaFace detector
└── src/                    # Anti-spoofing library (Minivision)
```

## Team

Developed by a team of 4 students as a college project.

## License

This project uses the Minivision Silent-Face-Anti-Spoofing library. Please refer to their [repository](https://github.com/minivision-ai/Silent-Face-Anti-Spoofing) for licensing details.

## Acknowledgments

- [Minivision](https://github.com/minivision-ai) for the anti-spoofing models
- [face_recognition](https://github.com/ageitgey/face_recognition) library by Adam Geitgey
