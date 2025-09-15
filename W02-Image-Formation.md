---
layout: default
---


# Week 2: Image Acquisition and Camera Systems
### Computer Vision Course - TIF-XXX

---

## **LECTURE OVERVIEW**

| **Aspect** | **Details** |
|------------|-------------|
| **Duration** | 100 minutes (45 + 10 break + 45) |
| **Learning Goal** | Understanding how digital images are created and factors affecting quality |
| **Delivery** | Theory + Hands-on demonstration |
| **Prerequisites** | Basic image concepts from Multimedia Systems |

---

## **LEARNING OBJECTIVES**

By the end of this lecture, students will be able to:
1. **Explain** how digital images are formed from light to pixels
2. **Identify** key camera parameters affecting image quality  
3. **Compare** different color spaces and their uses
4. **Analyze** image quality problems and their causes
5. **Apply** basic image acquisition using programming tools

---

## **SESSION 1: FUNDAMENTALS (45 minutes)**

### **Digital Image Basics Review (15 minutes)**
- **Image representation**: Pixels, resolution, bit depth
- **File formats**: JPEG, PNG, RAW differences
- **Coordinate systems**: Matrix indexing in programming
- **Mathematical view**: Images as numerical matrices

### **Camera Sensors and Technology (15 minutes)**
- **Sensor types**: CCD vs CMOS comparison
  - CCD: Better quality, higher power
  - CMOS: Faster, cheaper, lower power
- **Key characteristics**: Dynamic range, noise, sensitivity
- **Acquisition pipeline**: Light → Sensor → Digital conversion

### **Camera Parameters (15 minutes)**
- **Exposure triangle**: ISO, aperture, shutter speed
- **Focus and depth of field**: Sharp vs blurred regions
- **White balance**: Color temperature correction
- **Impact on image quality**: Trade-offs and optimization

**Live Demo**: Camera parameter changes showing real-time effects

---

## **SESSION 2: ADVANCED CONCEPTS (45 minutes)**

### **Image Formation Process (15 minutes)**
- **Physical principles**: Light reflection and absorption
- **Geometric projection**: 3D world to 2D image
- **Lens effects**: Distortion, aberrations, vignetting
- **Lighting considerations**: Direction, intensity, color

### **Color Spaces (15 minutes)**
- **RGB**: Standard for displays and cameras
- **HSV**: Better for color-based analysis
- **Grayscale**: Luminance representation
- **Conversion mathematics**: When and why to convert

**Programming Demo**: Color space conversion in Python/OpenCV

### **Image Quality Assessment (15 minutes)**
- **Common problems**:
  - Motion blur (camera shake)
  - Poor exposure (too dark/bright)
  - Noise (high ISO, poor lighting)
  - Wrong focus
- **Quality metrics**: Sharpness, contrast, signal-to-noise ratio
- **Optimization strategies**: Proper parameter selection

**Interactive Activity**: Students identify quality issues in sample images

---

## **PRACTICAL COMPONENTS**

### **Demonstrations**
1. **Camera parameter exploration**: Live adjustment showing effects
2. **Color space conversion**: Code demonstration with visual results
3. **Quality comparison**: Good vs poor acquisition examples

### **Student Activities**
- **Parameter prediction**: Guess settings from image characteristics
- **Problem identification**: Spot acquisition issues in test images
- **Basic coding**: Follow along with color conversion example

---

## **SIMPLIFIED ASSIGNMENT**

### **Image Acquisition Mini-Project**
**Duration**: 1 week | **Weight**: 5% of course grade

#### **Requirements**
1. **Image Collection** (50%)
   - Take 12-15 photos of the same subject with different settings:
     - 3 different ISO values (low, medium, high)
     - 3 different lighting conditions
     - 3 different focus settings
   - Document camera settings for each photo

2. **Simple Analysis** (50%)
   - Write short Python program to:
     - Load and display images
     - Convert to different color spaces
     - Calculate basic quality metrics (brightness, contrast)
   - Create simple comparison showing parameter effects

#### **Deliverables**
- **Image folder**: Organized photos with settings documentation
- **Python script**: Basic analysis code
- **Short report**: 2-3 pages explaining findings

#### **Evaluation Criteria**
- **Data quality**: Systematic collection with clear differences
- **Code functionality**: Working implementation of required features
- **Analysis**: Clear explanation of parameter effects on image quality

---

## **ESSENTIAL RESOURCES**

### **Required Reading**
- **Gonzalez & Woods Ch 2.3-2.4**: Image sensing and acquisition
- **OpenCV-Python Tutorial**: Basic image operations

### **Tools Needed**
- **Python + OpenCV**: For programming exercises
- **Camera (smartphone OK)**: For image acquisition
- **Sample images**: Provided for quality analysis

### **Quick Reference**
```python
# Essential OpenCV commands for Week 1
import cv2
import numpy as np

# Load image
img = cv2.imread('image.jpg')

# Color space conversion
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Basic quality metrics
brightness = np.mean(gray)
contrast = np.std(gray)
```

---

## **KEY TAKEAWAYS**

### **For Computer Vision Applications**
1. **Image quality matters**: Poor acquisition leads to poor CV results
2. **Parameter selection**: Choose settings based on application needs
3. **Color space selection**: Different spaces for different algorithms
4. **Preprocessing importance**: Fix acquisition issues before analysis

### **Practical Guidelines**
- **Good lighting**: Essential for quality results
- **Stable camera**: Avoid motion blur
- **Appropriate exposure**: Not too dark or bright
- **Consistent conditions**: For training data collection

---

## **PREPARATION FOR WEEK 2**

### **What's Next**
- **Advanced Image Processing**: Building on acquisition knowledge
- **Edge detection and filtering**: Using quality images for better results
- **Assignment connection**: Use Week 1 images for Week 2 processing

### **Self-Check Questions**
1. What camera settings would you use for outdoor vs indoor photography?
2. When would you convert RGB to grayscale vs HSV?
3. How can poor image acquisition affect edge detection algorithms?

---

## **INSTRUCTOR NOTES**

### **Time Management**
- **Theory sections**: 15 minutes each - stick to schedule
- **Demos**: Essential for understanding - don't skip
- **Student questions**: Save complex ones for after class

### **Common Issues**
- **Mathematical concepts**: Keep simple, focus on intuition
- **Programming anxiety**: Reassure beginners, provide support
- **Equipment problems**: Have backup plans and examples ready

### **Success Indicators**
- Students can explain sensor differences
- Students understand parameter trade-offs
- Students can run basic OpenCV operations
- Students connect acquisition to CV applications

---

**Course**: Computer Vision (TIF-XXX)  
**Academic Year**: 2025/2026  
**Version**: Simplified
