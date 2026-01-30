# Touchless Fingerprint Capture App

Developed by **Brahmi Systems OPC Pvt Ltd**, this application transforms a standard smartphone into a touchless fingerprint scanner. By leveraging advanced computer vision and OpenCV-powered image processing, it captures biometric data without physical contact.

---

##   Feature List

| Feature | Description | Notes / Status |
| :--- | :--- | :--- |
| **Camera Capture** | Utilizes the smartphone camera to capture high-resolution images of fingers. |Track A |
| **Real-time Preview** | Provides a live preview for the operator to focus the camera accurately. | Track A |
| **Position Guidance** | Dynamic text instructions ("MOVE CLOSER", "MOVE AWAY", "HOLD") to assist the operator. | Track A |
| **Visual Feedback** | Intelligent bounding box with **RED** (unsuitable) and **GREEN** (suitable) border indicators. | Track A |
| **Distance UI** | Display messages indicating height relative to the finger: MOVE LOW, MOVE HIGH, or OPTIMAL. | Track A |
| **Quality Control** | Automated post-capture quality checks with immediate PASS or FAIL feedback. | Track A |
| **Finger Segmentation** | Advanced processing to isolate the finger from the background for analysis. | Track A |
| **Multi-Capture** | Support for capturing several different finger images sequentially, one at a time. | Track A |
| **Minutiae Extraction** | Intelligent detection and mapping of fingerprint minutiae points. | Track B |
| **Enhanced Image Export** | Saves processed finger images with ridge-valley detail for further analysis. | Track B |
| **CSV Data Export** | Exports extracted minutiae coordinates and types into a structured CSV file. | Track B |
| **Ridge Detection** | Enhances and detects the ridge and valley patterns within the fingerprint using classical method. | Track B |
| **Finger Region Isolation**| Isolates the finger from the background in the captured image. | Track B |
| **Noise Reduction/Contrast Normalization**| CLAHE, Blue channel extraction, median blur, binarization | Track B |
| **Output an enhanced image**| Grayscale finger image, fingerprint image are output | Track B |
| **Ouput in ISO Resolution & Format**| FIR format file containing image in 500 DPI is generated | Track B |

---

##  Operating Procedure

To ensure high-quality biometric extraction, please follow these steps:

1. **Preparation:** Place the finger on or close to a flat surface.
2. **Initial Positioning:** Hold the smartphone as high as possible above the finger.
3. **Framing:** Ensure the finger is centered within the box in the camera preview.
4. **Guidance:** Press the **RESTART** button. Monitor the message at the top of the preview:
* Follow instructions to **MOVE LOW** or **MOVE HIGH**. _Each time_ the camera is moved to a new position - lower or higher - press **RESTART** button to get new guidance
* Wait until the instruction displays **OPTIMAL** and the box border turns **GREEN**.


5. **Capture:** Once the **OPTIMAL** state is reached, press the **START CAPTURE** button.
6. **Acquisition:** Hold the phone steady while the app completes the image acquisition.
7. **Review:** The app will display quality metrics. If the instruction tells you to **RETAKE**, please repeat the process.

---

###  Accessing Your Data

Captured images and CSV files can be found in the following directory:

`Internal storage\Android\data\com.example.touchlessfingerprint\files\Fingerprints\FingerprintDemo`

The files generated are:
1. **CSV file**: contains X, Y co-ordinates of the minutiae points in the fingerprint, geometric structure of the ridge at that point (Ending/Bifurcation)
2. **FIR file**: contains fingerprint image metadata as per ISO/IEC 19794-4:2005 and also the image itself in 500 DPI/PPI resolution
3. **Fingerprint image**: a file with the name 'fingerprint_xxxxxx.png' is generated that contains the image of the finger rendered such that ridges are in black color and rest is white
4. **Grayscale image**: a file with the name 'gray_fingerprint_xxxxxx.png' is generated with all colors removed highlighting the ridges
5. **RGB image**:  a file with the name 'rgb_fingerprint_xxxxxx.png' is generated and it is the original image captured
6. **FIR file image**: a file with the name 'fingerprint_xxxxxx.fir_fixed' contains the image that is stored in the FIR file
---

### Quality Metrics


| Metric | Explanation |
| :--- | :--- |
| **Sharpness** | Measures the optical focus of the fingerprint ridges. High sharpness is critical to ensure that ridge endings and bifurcations are distinct and not blurred into the background. |
| **Lighting** | Analyzes the brightness and contrast across the finger. This ensures that the ridges are not lost in deep shadows or "washed out" by over-exposure from external light sources. |
| **Finger Area** | Calculates the total surface area of the finger detected within the frame. This ensures the finger is positioned correctly to provide a sufficient number of minutiae points for a valid template. |

---

##  Open Source Libraries

The following open source software/libraries have been used:

* **OpenCV (Open Source Computer Vision Library)** 
* **Kotlin** 
* **Android Jetpack**

---

##  Limitations

1. **Background Contrast:** Current testing and optimization have been performed with the finger positioned over a **dark gray surface**. The app's behavior and accuracy with lighter backgrounds are currently undefined.
2. **Platform Support:** Currently, the application is only supported on **Android**.

---

## Download Latest APK

https://github.com/giridhar-narasimhamurthy/touchlessfingerprint/releases/download/v2.0.0/app-release.apk

## Older APKs
https://github.com/giridhar-narasimhamurthy/touchlessfingerprint/releases/download/v1.0.0/app-release.apk

---
