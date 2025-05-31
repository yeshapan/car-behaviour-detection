# Behavior Detection at Pedestrian Crossings

A computer vision project to analyze driver behavior at zebra crossings using YOLOv8 and object tracking. This project detects vehicles, estimates their speed, and classifies their behavior into categories such as:

## Project Objectives

1. Detect and track vehicles from surveillance footage.
2. Estimate their speed using frame-by-frame object tracking.
3. Classify vehicle behavior based on three positive traits:
  - **B1**: Reducing speed as the car is approaching the pedestrian crossing.
  - **B2**: Stopping at the crossing when a red light is shown, or pedestrians are crossing.
  - **B3**: Stop behind the crossing line.

> This project is inspired by work conducted with the Kuyesera AI Lab at MUBAS, under the leadership of Principal Investigator Dr. Amelia Taylor.

> NOTE that data is not included in this repo as it exceeds git's file size and data limit. Refer to the drive link below

> Here's the link to drive folder containing all the raw and data: https://drive.google.com/drive/folders/19tOeHkWPvRAXDDVmK2OMGSgiqTCMGbf3?usp=drive_link



## Project Structure
```bash
car-behaviour-detection/
│
├── models
│ ├── yolov8/
│
├── src/                          #source code for our project
│ ├── extract_frames.py           #extracts frames from video
│ ├── detect_yolo.py              #YOLOv8 detection logic
│ ├── track_sort.py               #vehicle tracking using SORT
│ ├── calculate_speed.py          #speed estimation logic
│ └── classify_behavior.py        #rule-based behavior classification
│
├── main.py                       #main orchestration pipeline
├── pyproject.toml                #Poetry config
├── poetry.lock                   #locked dependency versions
└── README.md                     #you're here!
```

## Drive Folder Structure
```bash
├── data/                         
│ ├── raw_videos/                 #original surveillance footages
│ ├── extracted_frames/           #frames extracted at 10 FPS
│ ├── visualized_tracked_frames/  #frames with objects (vehicles) detected and tracked with their ID (visuualized as bounding boxes)
│ ├── tracking_outputs/           #tracker outputs with IDs in a csv file
│ └── behavior_annotations/       #behavior labels
│
├── notebooks/                    #notebooks are just to test code in sections (on colab) before adding it  to src
│ ├── 1_extract_frames.ipynb           
│ ├── 2_detect_and_track.ipynb           
│ ├── 3_speed_estimation.ipynb
│ └── 4_behaviour_classification.ipynb
│
└── models
  ├── yolov8/
```

## Tech Stack

- **YOLOv8** – Object detection (via [Ultralytics](https://github.com/ultralytics/ultralytics))
- **OpenCV** – Frame extraction & visualization
- **SORT** – Vehicle tracking with consistent IDs
- **Poetry** – Python dependency & virtual environment management
  
## Setup Instructions (with Poetry)

### 1. Clone the repo

```bash
git clone https://github.com/your-username/behavior-detection-project.git
cd behavior-detection-project
```

### 2. Install Poetry (if not done so already)
Follow official instructions: https://python-poetry.org/docs/#installation
or
```bash
curl -sSL https://install.python-poetry.org | python3 -
```
> After installing poetry , add it to PATH and restart your terminal

### 3. Install dependencies
```bash
poetry install
```
### 4. Activate virtual environment
```bash
poetry shell
```
### 5. Run the full pipeline
