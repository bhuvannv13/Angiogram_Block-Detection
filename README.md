# Medical Image Processing Pipeline - Blockage Detection

This project implements a comprehensive image processing pipeline in Python using OpenCV and other key libraries to detect potential blockages in medical images. It performs pre-processing, enhancement, segmentation, and contour analysis, culminating in a diagnostic visualization of possible blockages.

## 📁 Dataset
The project uses sample medical images (e.g., `Type3.jpg`). Images are assumed to be stored in a Google Drive path, and accessed via Google Colab.

## 🧰 Libraries Used
- `pydicom`
- `numpy`
- `cv2 (OpenCV)`
- `matplotlib`
- `scipy`
- `skimage`

## 🔍 Pipeline Overview

### Step 1: Read & Display Original Image
- Load the image using `cv2.imread`.
- Display using `matplotlib.pyplot`.

### Step 2: Crop Borders
- Crop 10% of the image border to focus on the region of interest.

### Step 3: Grayscale Conversion
- Convert the cropped image to grayscale using `cv2.cvtColor`.

### Step 4: Brightness & Contrast Correction
- Automatically correct brightness and contrast using histogram clipping and linear scaling.

### Step 5: Noise Reduction
- Apply median blur to reduce noise while preserving edges.

### Step 6: Block-wise Segmentation
- Divide the image into blocks and overlay a grid for adaptive thresholding.

### Step 7: Adaptive Thresholding
- Use Gaussian and mean adaptive thresholding to highlight potential regions of interest.

### Step 8: Morphological Filtering & Contour Extraction
- Apply morphological operations (RECT, CROSS, ELLIPSE) and draw contours.

### Step 9: Threshold & Dilation
- Refine contours using binary thresholding and dilation.

### Step 10: Final Detection
- Use contour proximity logic to detect clustered regions.
- Visualize possible blockages with red circles and diagnostic text.

## 📸 Sample Outputs

Images generated at each stage are saved in:

These include:
- Original image
- Cropped image
- Brightness corrected
- Thresholded and contoured images
- Final detection output

## 🚀 Running the Code

1. Upload the medical image to Google Drive.
2. Open the [Colab Notebook](https://colab.research.google.com/) and run the cells step-by-step.
3. Adjust parameters like `block_size`, `min_contour_area`, and threshold constants for different image types.

## 📌 Note
- This pipeline works on JPEG images, not DICOM (`.dcm`) directly. For `.dcm` handling, use `pydicom` to load and convert pixel data.
- Intended for experimental/educational use only, not for clinical diagnostics.

## 🧠 Author
This pipeline was developed for a medical imaging project demonstrating classic computer vision techniques in Python and it is a recreated file and used for project purpose for gaining knowledge.

## 📄 License
This project is open-source under the [MIT License](LICENSE).
