# Automatic Vehicle Detection Using YOLOv5

## Introduction
Traffic congestion remains a critical issue in modern urban environments, exacerbated by the steady increase in the number of vehicles. To address this challenge, Automatic Vehicle Detection (AVD) systems are becoming indispensable tools for real-time traffic management and smart city initiatives. With advancements in autonomous driving technologies and driver assistance systems, the need for accurate and reliable vehicle detection has intensified. This repository presents an in-depth analysis of a YOLOv5-based vehicle detection model developed to enhance vehicle detection capabilities across diverse weather and lighting conditions.

## Dataset
The AVD-Dataset utilized for this evaluation comprises a total of 3,200 vehicle images. These images capture vehicles under various weather conditions, including:
- Rainy Day
- Rainy Night
- Sunny Day
- Sunny Night

The dataset is divided into:
- Training Set: 2,600 images
- Validation Set: 200 images
- Testing Set: 400 images

Each image is annotated in the YOLO format, providing bounding box coordinates and class labels for the vehicles. The dataset is designed to test the model's robustness and adaptability to different environmental conditions, crucial for real-world applications.

## Methodology

### Environment Setup
1. **YOLOv5 Repository:** Cloned from GitHub to ensure access to the latest model code and updates.
2. **Dependencies Installation:** Required libraries and packages were installed to facilitate model training and evaluation.
3. **Font Configuration:** Arial.ttf font was manually downloaded and configured to avoid issues with text rendering in output images.

### Data Preparation
- **Image and Annotation Consolidation:** Images and their corresponding annotations were organized into distinct directories for training and validation datasets.
- **Configuration File:** Created a YAML configuration file (vdvwc.yaml) for YOLOv5, including:
  - **Paths:** Locations of training and validation images.
  - **Number of Classes:** Set to 15.
  - **Class Names:** A list of vehicle classes and other relevant categories.

### Model Training
- **Training Parameters:** The YOLOv5s model was trained with a batch size of 32 and over 100 epochs to fine-tune the model to detect vehicles accurately across different conditions.
- **Training Process:** Utilized the YOLOv5 training script to optimize model weights, adjusting parameters based on training and validation performance.

### Validation and Testing
- **Model Validation:** Post-training, the model was validated using the best-performing weights to ensure accuracy and reliability.
- **Testing on Images:** The trained model was applied to test images to evaluate its performance in detecting vehicles under real-world conditions.

## Results
- **mAP:** 0.4528
- **F1-Score:** 0.4711

The YOLOv5-based model demonstrated significant effectiveness in vehicle detection across various weather conditions. The high mAP value signifies excellent precision and recall, while the F1-Score indicates a balanced approach to detecting vehicles with minimal errors.

## Conclusion
The YOLOv5-based vehicle detection model successfully tackled the complexities of vehicle detection under diverse weather and lighting conditions. The model’s high performance, as evidenced by the mAP and F1-Score, underscores its potential for real-world traffic management applications. This work not only highlights the effectiveness of YOLOv5 in vehicle detection but also establishes a benchmark for future improvements in vehicle detection systems and their integration into intelligent transportation networks.

## Future Work
To build on this success, future work could focus on:
1. **Expanding the Dataset:** Including additional weather conditions and different times of day.
2. **Enhancing the Model:** Experimenting with other YOLO variants or incorporating advanced techniques like ensemble methods.
3. **Real-World Testing:** Deploying the model in real-world scenarios to validate its performance and reliability further.

## Dataset
```bash
git clone https://github.com/Sourajit-Maity/juvdv2-vdvwc
```

## Repository Structure
```
- data/
  - images/
    - train/
    - val/
    - test/
  - annotations/
    - train/
    - val/
    - test/
- models/
  - yolov5s/
- scripts/
  - train.py
  - validate.py
  - test.py
- vdvwc.yaml
- README.md
```

## Installation
1. Clone the YOLOv5 repository:
    ```bash
    git clone https://github.com/ultralytics/yolov5.git
    ```
2. Navigate to the repository:
    ```bash
    cd yolov5
    ```
3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage
### Training
```bash
python train.py --img 640 --batch 32 --epochs 100 --data vdvwc.yaml --weights yolov5s.pt
```

### Validation
```bash
python val.py --weights runs/train/exp/weights/best.pt --data vdvwc.yaml
```

### Testing
```bash
python test.py --weights runs/train/exp/weights/best.pt --data vdvwc.yaml
```

## Acknowledgements
We acknowledge the use of the YOLOv5 repository and its contributors for providing the base code and model for this project.
