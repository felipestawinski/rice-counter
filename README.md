# Rice Counter

A computer vision project for identifying and counting rice grains in an image using image segmentation and connected component analysis.

## Overview

This project implements an automated rice grain counter using image segmentation techniques. The system processes grayscale images through the following pipeline:
- Image binarization using thresholding
- Connected component labeling using recursive flood fill
- Component filtering based on size constraints

## Dependencies

- Python 3.x
- OpenCV (`cv2`)
- NumPy

## Files

- main.py: Main program containing the segmentation algorithm
- arroz.bmp: Sample rice grain image for testing

## Usage

1. Place your image file in the project directory
2. Configure the parameters in main.py:
   ```python
   INPUT_IMAGE = 'arroz.bmp'  # Your input image
   NEGATIVO = False           # Invert the image if True
   THRESHOLD = 0.8            # Binarization threshold
   ALTURA_MIN = 15            # Minimum height for valid components
   LARGURA_MIN = 15           # Minimum width for valid components
   N_PIXELS_MIN = 30          # Minimum pixel count for valid components
   ```
3. Run the program:
   ```
   python pacote2-py/main.py
   ```

## Outputs

The program generates:
- `01 - binarizada.png`: The binary image after thresholding
- `02 - out.png`: Original image with bounding boxes around detected rice grains
- Terminal output showing execution time and number of components detected

## Algorithm

The algorithm consists of two main functions:
- `binariza()`: Performs thresholding to create a binary image
- `rotula()`: Labels connected components using flood fill algorithm
- `flood_fill()`: Helper function for recursive connected component labeling

## Author

Originally created by Bogdan T. Nassu, Federal University of Technology - Paraná (UTFPR)