# Face Recognition Attendance System

This project is a Python-based attendance system that uses facial recognition to identify individuals and mark their attendance in a CSV file. The system captures live video feed from a webcam, processes the frames to detect and recognize faces, and records the attendance along with the current timestamp.

## Features

- Recognizes pre-registered faces from images.
- Marks attendance in a CSV file with the date and time.
- Displays the name of recognized individuals on the video feed.
- Saves attendance data in a file named with the current date (e.g., `dd-mm-yy.csv`).

## Requirements

### Libraries

Install the following Python libraries before running the project:

- `face_recognition`: For facial recognition tasks.
- `numpy`: For numerical operations.
- `csv`: For writing attendance data.
- `datetime`: For timestamping attendance.
- `opencv-python`: For video capturing and image processing.

Install the required libraries using pip:
```bash
pip install face_recognition numpy opencv-python
```

### Hardware

- A webcam or any compatible video capturing device.

## Directory Structure

```
project/
├── faces/
│   ├── ankit.jpg
│   ├── rohan.jpg
├── attendance.py
```

- `faces/`: Directory containing pre-registered face images.
- `attendance.py`: The main script for running the attendance system.

## How to Run

1. Place the images of individuals to be recognized in the `faces/` directory.
   - Ensure that the images are clear and properly cropped to show the face.

2. Update the script with the names and paths of the images:
   ```python
   ankit_image = face_recognition.load_image_file("faces/ankit.jpg")
   rohan_image = face_recognition.load_image_file("faces/rohan.jpg")
   know_face_name = ["Ankit", "Rohan"]
   ```

3. Run the script:
   ```bash
   python attendance.py
   ```

4. Press `q` to stop the video feed and close the application.

## Output

- A CSV file named with the current date (e.g., `28-01-25.csv`) will be created in the project directory.
- Each row in the CSV file contains:
  - Name of the individual.
  - Timestamp of attendance.

## Notes

- Ensure proper lighting conditions for accurate face recognition.
- The script resizes video frames to improve performance, but this may affect recognition accuracy for smaller faces.
- Handle exceptions for cases where no face is detected in the provided images.

## Example

- **Input**:
  - Images: `ankit.jpg`, `rohan.jpg`
  - Live video feed from webcam.

- **Output**:
  ```csv
  Name,Time
  Ankit,15-30-45
  Rohan,15-31-10
  ```

## Future Improvements

- Add support for dynamic registration of new faces.
- Integrate with a database for more robust attendance management.
- Enhance recognition accuracy with better preprocessing techniques.
- Implement multi-camera support for larger environments.

## License

This project is open-source and available for modification and redistribution.
