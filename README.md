# Deep-Learning-Sign-Detection

# Smart Cities Laboratory: Traffic Sign Detection using Deep Learning

## **Overview**
This project focuses on improving traffic safety by analyzing road signs in horizontal curves using a deep learning-based detection pipeline. Given that over 25% of fatal crashes occur on horizontal curves, the goal is to assess the visibility, placement, and condition of these traffic signs using onboard video recordings and a YOLOv8-based object detection model.

## **Background**
- Horizontal curves are a major risk factor in road safety, with a high percentage of single-vehicle crashes occurring due to inadequate sign visibility or placement.
- Traditional road signs often fail to mitigate crashes effectively, raising concerns about their effectiveness.
- The project aims to identify potential improvements by leveraging AI-based detection of traffic signs.

## **Solution**
The Smart Cities Laboratory developed a **deep-learning-based sign detection pipeline** that:
- Analyzes onboard video recordings.
- Evaluates the condition and placement of traffic signs.
- Uses MUTCD (Manual on Uniform Traffic Control Devices) codes to classify and assess sign types.

## **Methodology**
### **Data Exploration and Preparation**
- Analyzed dataset characteristics: blur, brightness, distribution per class, and image composition.
- Examined average number of images per sign class.
- Prepared the dataset for model training and optimized preprocessing.

### **Model Training & Deployment**
- Transitioned from YOLOR (2021) to **YOLOv8-NANO (2023)** to improve detection performance.
- Trained the model over **100 epochs**, with convergence occurring between **10-20 epochs**.
- Evaluated multiple model sizes (Nano to Extra-Large) to analyze differences in performance.

### **Detection Phase**
- Used trained weights to process video footage.
- Implemented bounding boxes with labels indicating **sign class and confidence score**.
- Set a detection threshold of **0.50** to determine positive identifications.

## **Results & Insights**
- **Image Size Impact**: Increasing resolution from **320px → 640px → 1280px** significantly improved performance.
- **Model Size Analysis**: No clear correlation between model size and detection accuracy.
- **False Positives**:
  - The model misclassified **traffic lights, pedestrian displays, and the backside of signs**.
  - Struggled with **compound signs** (e.g., misidentifying a "No Parking" sign as a speed limit sign).
- **Distance Challenges**: Struggled to detect signs that were far away.

## **Challenges & Recommendations**
### **Technical Challenges**
- **Remote Workspace Issues**: GPU and Remote Desktop access was inconsistent, making it harder to train models effectively.
- **Collaboration Gaps**: Limited interaction with other researchers in the laboratory reduced opportunities for feedback.

### **Model Improvement Recommendations**
- Improve dataset **diversity and augmentation**, especially for poorly represented classes.
- Add **bounding box annotations** for diamond-shaped signs to improve distinction between front and back.
- Expand the dataset to include additional MUTCD sign classes (e.g., stop signs, regulatory signs).
- Review output videos and refine training methodology based on misclassification patterns.

## **Conclusion**
This project provided valuable insights into deep-learning applications for **traffic safety and road sign detection**. The next steps involve refining the model further, comparing YOLOv8 against previous iterations (YOLOR), and exploring real-world deployment strategies for road safety improvements.
