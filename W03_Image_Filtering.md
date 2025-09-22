---
layout: default
---

# Week 3: Image Filtering
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

This assignment focuses on implementing and analyzing basic image filtering techniques that form the foundation of computer vision. You will work with spatial filtering and edge detection algorithms using images captured from your own camera. The goal is to understand how these fundamental techniques work through hands-on implementation.

## Learning Objectives

By completing this assignment, you will be able to:
- Implement basic spatial filtering operations from scratch
- Apply and compare different edge detection algorithms
- Understand the mathematical foundations of image convolution
- Develop practical skills with OpenCV and image processing
- Analyze filtering effects on real-world images

## Technical Requirements

### Environment Setup
- **Platform**: Google Colab (free tier sufficient)
- **Programming Language**: Python 3.x
- **Required Libraries**: 
  - OpenCV (`cv2`)
  - NumPy (`numpy`)
  - Matplotlib (`matplotlib.pyplot`)

### Dataset - Your Own Images
You will capture and use your own images for this assignment:

**Required Images (minimum 3):**
1. **Portrait/Face Image**: Clear photo of a person (yourself or friend with permission)
2. **Text/Document**: Photo of a book page, handwritten notes, or printed document
3. **Outdoor Scene**: Landscape, building, or street scene with various edges and textures

**Image Requirements:**
- **Resolution**: At least 640x480 pixels
- **Format**: JPG or PNG
- **Quality**: Clear, well-lit images (avoid blurry photos)
- **Content**: Images should have visible edges, textures, and details for filtering analysis

**Capture Guidelines:**
- Use your smartphone or camera
- Ensure good lighting conditions
- Avoid excessive shadows or overexposure
- Include variety in content (faces, text, natural scenes)

---

## Assignment Tasks

### **Part 1: Basic Spatial Filtering (40 points)**

#### Task 1.1: Implement Convolution Operation (15 points)
Create a function that performs 2D convolution without using built-in OpenCV functions.

```python
def custom_convolution(image, kernel, padding='zero'):
    """
    Implement 2D convolution operation
    
    Parameters:
    - image: Input image (2D numpy array for grayscale)
    - kernel: Convolution kernel (2D numpy array)
    - padding: Padding method ('zero', 'constant')
    
    Returns:
    - filtered_image: Convolution result
    """
    # Your implementation here
    pass
```

**Requirements:**
- Handle zero padding and constant padding
- Support grayscale images (convert your color images to grayscale)
- Test with simple 3x3 kernels first
- Compare results with OpenCV's `cv2.filter2D()`

**Testing:**
- Apply your function to a simple 3x3 averaging kernel
- Verify correctness by comparing with OpenCV results
- Show side-by-side comparison of original vs filtered image

#### Task 1.2: Basic Filtering Operations (25 points)
Implement and apply the following filters to your captured images:

1. **Gaussian Blur Filter (10 points)**
   ```python
   def gaussian_kernel(size, sigma):
       """Create a Gaussian kernel"""
       # Your implementation here
       pass
   
   def apply_gaussian_blur(image, kernel_size, sigma):
       """Apply Gaussian blur using your convolution function"""
       # Your implementation here
       pass
   ```
   - Create Gaussian kernels of sizes 5x5 and 9x9
   - Apply to your portrait image to create blur effect
   - Compare with OpenCV's `cv2.GaussianBlur()`

2. **Box Filter (Averaging) (8 points)**
   ```python
   def box_filter(image, kernel_size):
       """Apply box filter for smoothing"""
       # Your implementation here
       pass
   ```
   - Implement simple averaging filter with 3x3 and 5x5 kernels
   - Apply to your document image
   - Analyze the smoothing effect on text clarity

3. **Unsharp Masking (7 points)**
   ```python
   def unsharp_mask(image, sigma, alpha):
       """
       Implement image sharpening using unsharp mask
       Formula: sharpened = original + α * (original - blurred)
       """
       # Your implementation here
       pass
   ```
   - Test with different α values (0.5, 1.0, 2.0)
   - Apply to your outdoor scene image
   - Show the sharpening effect on edges and details

**Deliverables for Part 1:**
- Working implementations of all functions
- Visual results showing before/after filtering
- Brief analysis of each filter's effect on different image types

### **Part 2: Edge Detection Algorithms (60 points)**

#### Task 2.1: Gradient-Based Edge Detection (35 points)

1. **Sobel Edge Detector (15 points)**
   ```python
   def sobel_edge_detection(image):
       """
       Implement Sobel edge detection
       
       Parameters:
       - image: Input grayscale image
       
       Returns:
       - magnitude: Edge magnitude image
       - direction: Edge direction image
       """
       # Sobel kernels
       sobel_x = np.array([[-1, 0, 1], [-2, 0, 2], [-1, 0, 1]])
       sobel_y = np.array([[-1, -2, -1], [0, 0, 0], [1, 2, 1]])
       
       # Your implementation here
       pass
   ```
   - Apply Sobel operator to detect edges in your images
   - Calculate both magnitude and direction of gradients
   - Display results with proper visualization

2. **Prewitt Edge Detector (10 points)**
   ```python
   def prewitt_edge_detection(image):
       """Implement Prewitt edge detection"""
       # Prewitt kernels  
       prewitt_x = np.array([[-1, 0, 1], [-1, 0, 1], [-1, 0, 1]])
       prewitt_y = np.array([[-1, -1, -1], [0, 0, 0], [1, 1, 1]])
       
       # Your implementation here
       pass
   ```
   - Compare Prewitt results with Sobel on the same images
   - Analyze differences in edge detection quality

3. **Roberts Cross-Gradient (10 points)**
   ```python
   def roberts_edge_detection(image):
       """Implement Roberts cross-gradient operator"""
       # Roberts kernels
       roberts_x = np.array([[1, 0], [0, -1]])
       roberts_y = np.array([[0, 1], [-1, 0]])
       
       # Your implementation here
       pass
   ```
   - Apply Roberts operator to your images
   - Compare with Sobel and Prewitt results

#### Task 2.2: Edge Detection Comparison and Analysis (25 points)

1. **Comparative Visualization (15 points)**
   - Create a comparison grid showing results of all three edge detectors on each of your images
   - Use consistent visualization (same colormap, scaling)
   - Include original image for reference

2. **Qualitative Analysis (10 points)**
   Write a brief analysis addressing:
   - Which edge detector works best for different types of content (faces, text, outdoor scenes)?
   - How do the different operators handle noise?
   - What are the trade-offs between sensitivity and noise robustness?
   - Which method preserves fine details better?

**Deliverables for Part 2:**
- Working implementations of all three edge detectors
- Comparative visualization grid for all your images
- Written analysis of results and method comparison

---

## Implementation Guidelines

### Code Structure
Your Google Colab notebook should be organized as follows:

```
1. Setup and Imports
2. Image Loading and Preprocessing
   2.1 Load your captured images
   2.2 Convert to grayscale
   2.3 Display original images
3. Part 1: Spatial Filtering
   3.1 Custom Convolution Implementation
   3.2 Gaussian Blur Implementation and Testing
   3.3 Box Filter Implementation and Testing
   3.4 Unsharp Masking Implementation and Testing
   3.5 Part 1 Results Summary
4. Part 2: Edge Detection
   4.1 Sobel Edge Detection Implementation
   4.2 Prewitt Edge Detection Implementation  
   4.3 Roberts Edge Detection Implementation
   4.4 Comparative Analysis and Visualization
5. Final Conclusions
```

### Documentation Requirements
- **Clear comments** explaining each step of your algorithms
- **Docstrings** for all functions with parameter descriptions
- **Markdown cells** explaining the theory behind each method
- **Proper captions** for all images and plots
- **Code organization** with logical sections

### Image Handling Guidelines
```python
# Example image loading and preprocessing
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load and preprocess your images
def load_and_preprocess_image(image_path, max_size=512):
    """Load image and resize if necessary"""
    image = cv2.imread(image_path)
    image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
    
    # Resize if too large (for faster processing)
    height, width = image.shape[:2]
    if max(height, width) > max_size:
        scale = max_size / max(height, width)
        new_width = int(width * scale)
        new_height = int(height * scale)
        image = cv2.resize(image, (new_width, new_height))
    
    return image

# Convert to grayscale for processing
def rgb_to_grayscale(image):
    """Convert RGB image to grayscale"""
    return np.dot(image[...,:3], [0.2989, 0.5870, 0.1140])
```

---

## Evaluation Criteria

### Technical Implementation (70 points)
- **Custom Convolution** (15 points): Correct implementation without OpenCV
- **Spatial Filtering** (25 points): Proper implementation of Gaussian, box, and unsharp mask filters
- **Edge Detection** (30 points): Correct implementation of Sobel, Prewitt, and Roberts operators

### Analysis and Results (20 points)
- **Visual Results** (10 points): Clear, well-presented filter and edge detection results
- **Comparative Analysis** (10 points): Thoughtful comparison of different methods

### Code Quality and Documentation (10 points)
- **Code Organization** (5 points): Clean, readable code structure
- **Documentation** (5 points): Good comments and explanations

### Bonus Points (up to 10 points)
- **Creative Image Choices**: Interesting or challenging images for testing
- **Additional Analysis**: Extra experiments or insights
- **Code Efficiency**: Optimized implementations

---

## Submission Requirements

### What to Submit
1. **Google Colab Notebook** (.ipynb file)
   - Include all code, outputs, and analysis
   - Ensure all cells are executed and results are visible
   - Make sure the notebook is shared with instructor access

2. **Your Original Images**
   - Upload your 3+ original images to your Colab environment
   - Include them in the notebook execution

### Submission Checklist
- [ ] All required functions are implemented from scratch
- [ ] Custom convolution function works correctly
- [ ] All three filters (Gaussian, box, unsharp mask) are implemented and tested
- [ ] All three edge detectors (Sobel, Prewitt, Roberts) are implemented
- [ ] Your own captured images are used throughout
- [ ] Results are clearly visualized with proper labels
- [ ] Comparative analysis is included
- [ ] Code is well-commented and organized
- [ ] Notebook runs without errors

### File Naming
- Notebook: `LastName_FirstName_CV_ImageFiltering.ipynb`
- Example: `Smith_John_CV_ImageFiltering.ipynb`

---

## Resources and Tips

### Essential NumPy Operations
```python
# Useful NumPy functions for this assignment
np.zeros_like()     # Create zero array with same shape
np.pad()            # Add padding to arrays
np.sqrt()           # Square root for magnitude calculation
np.arctan2()        # Calculate gradient direction
np.clip()           # Clip values to valid range [0, 255]
```

### Visualization Tips
```python
# Good visualization practice
plt.figure(figsize=(15, 5))
plt.subplot(1, 3, 1)
plt.imshow(original, cmap='gray')
plt.title('Original')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(filtered, cmap='gray')
plt.title('Filtered')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edges')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### Common Issues and Solutions
1. **Image too large**: Resize images to 512x512 max for faster processing
2. **Wrong data types**: Ensure images are in proper format (0-255 for uint8)
3. **Kernel size**: Start with small kernels (3x3, 5x5) for testing
4. **Padding issues**: Be careful with array bounds in convolution

---

## Timeline

| Days 1-2 | Set up environment, capture images, implement convolution |
| Days 3-4 | Implement and test spatial filters |
| Days 5-6 | Implement edge detection algorithms |
| Day 7 | Final testing, documentation, and submission |

---

## Getting Help

### Common Questions
- **Q**: Can I use smartphone images?  
  **A**: Yes, smartphone photos are perfect for this assignment.

- **Q**: What if my convolution results don't exactly match OpenCV?  
  **A**: Small differences due to different padding methods are acceptable.

- **Q**: Should I implement color image filtering?  
  **A**: No, work with grayscale images for simplicity.

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

*This simplified assignment focuses on core image filtering concepts. Take time to understand the mathematical principles behind each algorithm. Good luck!*

---


**Course**: Computer Vision (TIF456)  
**Academic Year**: 2025/2026  
