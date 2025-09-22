---
layout: default
---

# Week 2: Image Filtering
{: .no_toc .text-delta }

**Author:** *Irwan Prasetya Gunawan* \
**Contact:** [irwan.gunawan@bakrie.ac.id](mailto:irwan.gunawan@bakrie.ac.id) / [irwan@ieee.org](mailto:irwan@ieee.org) \
**Published Date:** 22 September 2025

## Table of Contents
{: .no_toc .text-delta }

* TOC
{:toc}



---

## **Assignment Overview**

This assignment focuses on implementing and analyzing various image filtering techniques that form the foundation of computer vision. You will work with classical image processing algorithms including spatial filtering, edge detection, and morphological operations. The goal is to understand how these fundamental techniques work and their applications in computer vision systems.

## **Learning Objectives**

By completing this assignment, you will be able to:
- Implement basic spatial filtering operations from scratch
- Apply and compare different edge detection algorithms
- Understand morphological operations and their applications
- Analyze the effectiveness of different filtering techniques
- Develop practical skills with OpenCV and image processing

## **Technical Requirements**

### **Environment Setup**
- **Platform**: Google Colab (free tier sufficient)
- **Programming Language**: Python 3.x
- **Required Libraries**: 
  - OpenCV (`cv2`)
  - NumPy (`numpy`)
  - Matplotlib (`matplotlib.pyplot`)
  - SciPy (`scipy`)

### **Dataset**
You will work with the provided test images:
1. **Natural Image**: High-resolution color photograph
2. **Document Image**: Scanned text document
3. **Medical Image**: X-ray or MRI scan (grayscale)
4. **Noisy Image**: Image with added noise for filtering tests

*Download links will be provided in the assignment announcement.*

---

## **Assignment Tasks**

### **Part 1: Basic Spatial Filtering (25 points)**

#### Task 1.1: Implement Convolution Operation (10 points)
Create a function that performs 2D convolution without using built-in OpenCV functions.

```python
def custom_convolution(image, kernel, padding='zero'):
    """
    Implement 2D convolution operation
    
    Parameters:
    - image: Input image (2D numpy array)
    - kernel: Convolution kernel (2D numpy array)
    - padding: Padding method ('zero', 'reflect', 'constant')
    
    Returns:
    - filtered_image: Convolution result
    """
    # Your implementation here
    pass
```

**Requirements:**
- Handle different padding methods
- Support both grayscale and color images
- Compare results with OpenCV's `cv2.filter2D()`

#### Task 1.2: Basic Filtering Operations (15 points)
Implement and apply the following filters:

1. **Gaussian Blur**
   - Create Gaussian kernels of different sizes (3x3, 5x5, 7x7)
   - Apply to remove noise from the noisy test image
   - Compare with OpenCV's `cv2.GaussianBlur()`

2. **Box Filter**
   - Implement simple averaging filter
   - Test different kernel sizes
   - Analyze the smoothing effect

3. **Unsharp Masking**
   - Implement image sharpening using unsharp mask technique
   - Formula: `sharpened = original + α * (original - blurred)`
   - Test different α values

**Deliverables:**
- Implementation of all three filters
- Comparative analysis with visual results
- Discussion of when to use each filter type

### **Part 2: Edge Detection Algorithms (30 points)**

#### Task 2.1: Gradient-Based Edge Detection (15 points)
Implement the following edge detection methods:

1. **Sobel Edge Detector**
   ```python
   def sobel_edge_detection(image, direction='both'):
       """
       Implement Sobel edge detection
       
       Parameters:
       - image: Input grayscale image
       - direction: 'horizontal', 'vertical', or 'both'
       
       Returns:
       - edges: Edge magnitude image
       - direction_map: Edge direction map (for 'both')
       """
       # Your implementation here
       pass
   ```

2. **Prewitt Edge Detector**
   - Similar to Sobel but with different kernels
   - Compare results with Sobel detector

3. **Roberts Cross-Gradient**
   - Implement the simple 2x2 gradient operator
   - Analyze performance on different image types

**Requirements:**
- Implement from scratch using your convolution function
- Calculate both magnitude and direction of gradients
- Compare with OpenCV implementations

#### Task 2.2: Canny Edge Detection (15 points)
Implement a simplified version of the Canny edge detector:

```python
def canny_edge_detection(image, low_threshold, high_threshold, sigma=1.0):
    """
    Simplified Canny edge detection implementation
    
    Parameters:
    - image: Input grayscale image
    - low_threshold: Lower threshold for edge linking
    - high_threshold: Upper threshold for edge detection
    - sigma: Standard deviation for Gaussian smoothing
    
    Returns:
    - edges: Binary edge image
    """
    # Your implementation steps:
    # 1. Gaussian smoothing
    # 2. Gradient calculation
    # 3. Non-maximum suppression (simplified)
    # 4. Double thresholding
    # 5. Edge tracking (simplified)
    pass
```

**Requirements:**
- Implement all major steps of Canny algorithm
- Test different threshold values
- Compare with OpenCV's `cv2.Canny()`
- Analyze parameter sensitivity

### **Part 3: Morphological Operations (25 points)**

#### Task 3.1: Basic Morphological Operations (15 points)
Implement fundamental morphological operations:

1. **Erosion and Dilation**
   ```python
   def morphological_operation(image, kernel, operation='erosion'):
       """
       Implement basic morphological operations
       
       Parameters:
       - image: Binary input image
       - kernel: Structuring element
       - operation: 'erosion' or 'dilation'
       
       Returns:
       - result: Processed binary image
       """
       # Your implementation here
       pass
   ```

2. **Opening and Closing**
   - Implement as combinations of erosion and dilation
   - Test on noisy binary images

3. **Gradient and Top-hat**
   - Morphological gradient: dilation - erosion
   - Top-hat: original - opening

**Requirements:**
- Create different structuring elements (rectangular, circular, cross)
- Test on binary images extracted from your test dataset
- Compare with OpenCV implementations

#### Task 3.2: Advanced Morphological Analysis (10 points)
Apply morphological operations for practical problems:

1. **Noise Removal**: Clean up binary document images
2. **Shape Analysis**: Extract and count objects in binary images
3. **Text Processing**: Separate touching characters in document images

### **Part 4: Comparative Analysis and Applications (20 points)**

#### Task 4.1: Filter Comparison Study (10 points)
Create a comprehensive comparison of filtering techniques:

1. **Noise Reduction Effectiveness**
   - Add different types of noise (Gaussian, salt-and-pepper, speckle)
   - Test various filters on each noise type
   - Measure performance using PSNR and SSIM metrics

2. **Edge Preservation Analysis**
   - Compare how different filters affect edge preservation
   - Use edge-aware metrics for evaluation

3. **Computational Performance**
   - Time different implementations
   - Analyze complexity trade-offs

#### Task 4.2: Real-World Application (10 points)
Choose one of the following applications and implement a complete solution:

**Option A: Document Image Enhancement**
- Preprocess scanned document for OCR
- Remove noise, enhance contrast, sharpen text
- Implement complete pipeline

**Option B: Medical Image Enhancement**
- Enhance medical image for better visualization
- Apply appropriate filtering for noise reduction
- Highlight important features using edge detection

**Option C: Quality Control System**
- Detect defects in manufactured products
- Use edge detection and morphological operations
- Create automated inspection pipeline

---

## **Implementation Guidelines**

### **Code Structure**
Your Google Colab notebook should be organized as follows:

```
1. Setup and Imports
2. Helper Functions
3. Part 1: Spatial Filtering
   3.1 Custom Convolution Implementation
   3.2 Basic Filters Implementation
   3.3 Results and Analysis
4. Part 2: Edge Detection
   4.1 Gradient-based Methods
   4.2 Canny Implementation
   4.3 Comparative Analysis
5. Part 3: Morphological Operations
   5.1 Basic Operations
   5.2 Advanced Applications
6. Part 4: Comprehensive Analysis
   6.1 Filter Comparison
   6.2 Real-world Application
7. Conclusions and Insights
```

### **Documentation Requirements**
- **Clear comments** explaining algorithm steps
- **Docstrings** for all functions
- **Markdown cells** explaining theory and methodology
- **Visual results** with proper captions
- **Performance analysis** with quantitative metrics

### **Testing Protocol**
1. **Correctness Testing**: Compare your implementations with OpenCV functions
2. **Parameter Sensitivity**: Test different parameter values
3. **Boundary Cases**: Test with edge cases (small images, extreme parameters)
4. **Performance Testing**: Measure execution time for different image sizes

---

## **Evaluation Criteria**

### **Technical Implementation (60 points)**
- **Code Quality** (20 points): Clean, efficient, well-documented code
- **Algorithm Correctness** (25 points): Proper implementation of algorithms
- **Testing and Validation** (15 points): Comprehensive testing with OpenCV comparison

### **Analysis and Insights (25 points)**
- **Comparative Analysis** (15 points): Thorough comparison of different methods
- **Parameter Studies** (10 points): Analysis of parameter effects

### **Presentation and Documentation (15 points)**
- **Code Organization** (5 points): Clear notebook structure
- **Visual Presentation** (5 points): Quality of plots and figures
- **Written Analysis** (5 points): Clear explanations and insights

### **Bonus Points (up to 10 points)**
- **Creative Applications**: Novel use of filtering techniques
- **Performance Optimization**: Efficient implementations
- **Advanced Features**: Implementation of additional algorithms

---

## **Submission Requirements**

### **File Submission**
1. **Google Colab Notebook** (.ipynb file)
   - Include all code, results, and analysis
   - Ensure all cells are executed and outputs are visible
   - Share link should be accessible to instructors

2. **README File** (.txt or .md)
   - Brief description of your implementation
   - Instructions for running the code
   - List of external resources used

### **Submission Checklist**
- [ ] All required functions are implemented
- [ ] Code runs without errors in Google Colab
- [ ] All visualizations are included with proper captions
- [ ] Comparative analysis is complete
- [ ] Code is well-documented with comments
- [ ] Performance metrics are calculated and reported
- [ ] Real-world application is fully implemented
- [ ] Notebook is organized and easy to follow

### **Academic Integrity**
- You may discuss concepts with classmates, but all code must be your own
- Properly cite any external resources or references used
- Do not copy code from online sources without attribution
- Plagiarism will result in zero points for the assignment

---

## **Resources and References**

### **Primary References**
- Gonzalez & Woods, "Digital Image Processing", Chapters 3, 9, 10
- OpenCV-Python Tutorials: https://docs.opencv.org/master/d6/d00/tutorial_py_root.html

### **Helpful Links**
- **NumPy Documentation**: https://numpy.org/doc/stable/
- **Matplotlib Gallery**: https://matplotlib.org/stable/gallery/index.html
- **SciPy Image Processing**: https://docs.scipy.org/doc/scipy/reference/ndimage.html

### **Sample Code Templates**
Templates for common operations will be provided in the course materials folder.

---

## **Getting Help**

### **Office Hours**
- **Instructor**: [Day/Time]
- **Teaching Assistant**: [Day/Time]

### **Discussion Forum**
Use the course discussion forum for:
- Clarification questions about requirements
- Technical issues with Google Colab
- General discussion about algorithms

### **Common Issues**
1. **Memory limitations in Colab**: Use smaller test images for development
2. **Slow execution**: Optimize loops and use vectorized operations
3. **Import errors**: Ensure all required libraries are installed

---

## **Timeline and Milestones**

| Week | Milestone | Deliverable |
|------|-----------|-------------|
| Week 1 | Environment setup and Part 1 | Basic filtering implementations |
| Week 1.5 | Parts 2-3 completion | Edge detection and morphology |
| Week 2 | Analysis and documentation | Complete assignment |

**Final Due Date**: [Insert specific date and time]  
**Late Submission Policy**: -10% per day late (up to 3 days)

---

*This assignment is designed to build strong foundations in classical computer vision techniques. Take time to understand the algorithms conceptually before implementing them. Good luck!*



---


**Course**: Computer Vision (TIF456)  
**Academic Year**: 2025/2026  
