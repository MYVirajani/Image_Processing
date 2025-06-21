# EC7212 Computer Vision Assignment 1

**Student:** Virajani M.Y  
**Reg No:** EG/2020/4254

## Overview

This project implements four fundamental image processing operations for computer vision:

1. **Intensity Level Quantization** - Reduces color/intensity levels to powers of 2
2. **Neighborhood Averaging Filters** - Applies spatial smoothing with different kernel sizes
3. **Image Geometric Transformations** - Performs image rotation (45° and 90°)
4. **Block-based Resolution Reduction** - Reduces spatial resolution using block averaging

## Requirements

```bash
pip install opencv-python numpy matplotlib pathlib
```

## Quick Start

1. **Prepare your image:**

   - Place your input image in the project directory
   - Supported formats: JPG, PNG, BMP, TIFF

2. **Configure the script:**

   ```python
   IMAGE_FILE = "your_image.jpg"  # Change to your image filename
   color_processing = True        # Set False for grayscale processing
   ```

3. **Run the program:**
   ```bash
   python cv_assignment.py
   ```

## Features

### Task 1: Intensity Level Quantization

- Reduces intensity levels to: 2, 4, 8, 16, 32, 64, 128 levels
- Works with both color and grayscale images
- Demonstrates quantization effects on image quality

### Task 2: Spatial Averaging Filters

- Applies averaging filters with kernel sizes: 3×3, 10×10, 20×20
- Shows progressive smoothing effects
- Reduces noise while blurring fine details

### Task 3: Image Rotation

- Rotates images by 45° and 90°
- Preserves entire image content (no cropping)
- Demonstrates geometric transformations

### Task 4: Spatial Resolution Reduction

- Uses block averaging with block sizes: 3×3, 5×5, 7×7
- Reduces spatial resolution while maintaining overall structure
- Creates pixelated/mosaic effects

## Output Structure

```
assignment_results/
├── original_input.png
├── task1_quantized_2levels.png
├── task1_quantized_4levels.png
├── ...
├── task2_averaging_3x3.png
├── task2_averaging_10x10.png
├── task2_averaging_20x20.png
├── task3_rotation_45deg.png
├── task3_rotation_90deg.png
├── task4_resolution_3x3blocks.png
├── task4_resolution_5x5blocks.png
└── task4_resolution_7x7blocks.png
```

## Usage Examples

### Color Image Processing

```python
processor = CVAssignmentProcessor("image.jpg", color_mode=True)
processor.process_all_assignments()
```

### Grayscale Processing

```python
processor = CVAssignmentProcessor("image.jpg", color_mode=False)
processor.process_all_assignments()
```

### Individual Task Execution

```python
processor = CVAssignmentProcessor("image.jpg")

# Run specific tasks
processor.execute_task1_quantization()
processor.execute_task2_filtering()
processor.execute_task3_rotation()
processor.execute_task4_resolution_reduction()
```

## Key Methods

| Method                                  | Description                                     |
| --------------------------------------- | ----------------------------------------------- |
| `quantize_intensity_levels(levels)`     | Quantizes image to specified intensity levels   |
| `apply_neighborhood_averaging(size)`    | Applies averaging filter with given kernel size |
| `perform_rotation(angle)`               | Rotates image by specified angle                |
| `reduce_spatial_resolution(block_size)` | Reduces resolution using block averaging        |

## Troubleshooting

**Image not loading:**

- Check file path and filename
- Ensure image format is supported
- Verify file exists in the directory

**Memory issues:**

- Use smaller images for testing
- Consider grayscale mode for large images

**Output quality:**

- Results are saved as PNG for best quality
- Original aspect ratios are preserved

## Technical Notes

- **Color Mode:** Processes RGB channels independently
- **Grayscale Mode:** Direct intensity processing
- **Rotation:** Uses OpenCV's affine transformation with automatic size adjustment
- **Block Averaging:** Non-overlapping blocks with mean calculation
- **Output Format:** All results saved as PNG files with descriptive names

## Assignment Objectives

This implementation demonstrates understanding of:

- Digital image representation and manipulation
- Spatial domain filtering techniques
- Geometric transformations in computer vision
- Resolution and quantization effects on image quality
- Python programming for image processing tasks
