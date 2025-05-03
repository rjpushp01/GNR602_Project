# Multispectral Image Compression Using Self-Organizing Maps (SOM)

## Overview
This project demonstrates the compression of multispectral satellite imagery using **Self-Organizing Maps (SOM)** in Python. It covers:
- Stacking multiple spectral bands
- Visualizing true-color composites
- Applying SOM-based compression with various grid sizes
- Evaluating reconstruction quality using **Mean Squared Error (MSE)**

---

## Features

- **Multi-band Stacking**  
  Combine multiple single-band TIFF files into a single multi-band image using `rasterio`.

- **True-Color Visualization**  
  Display RGB composites from the multispectral dataset.

- **SOM Implementation**  
  Custom Python class implementing SOM with configurable grid sizes and learning parameters.

- **Image Compression**  
  Compress images by mapping each pixel to its closest SOM codebook vector.

- **Quality Assessment**  
  Evaluate performance using **Mean Squared Error (MSE)**.

- **Visualization Includes**:
  - Compressed RGB images and their cluster positions
  - SOM codebook grids
  - Reconstructed spectral bands
  - MSE vs. SOM grid size plot

---

## File Structure

```
SOM_GNR602_Project.ipynb     # Main Jupyter Notebook
README.md                    # Project description and instructions
```

---

## Requirements

- Python 3.7+
- Jupyter Notebook

### Required Python Packages

- numpy  
- matplotlib  
- scikit-image  
- rasterio  
- pillow  
- tkinter

### Installation

```bash
pip install numpy matplotlib scikit-image rasterio pillow
```

---

## Usage

1. **Prepare Input Bands**  
   Place single-band TIFF files (e.g., Sentinel-2 bands) in a known directory.

2. **Stack Bands**  
   The notebook stacks selected bands into a multi-band TIFF using `rasterio`.

3. **Load and Visualize**  
   The multi-band image is loaded and displayed as a true-color composite.

4. **Train SOM**  
   Run the SOM compression for various grid sizes (e.g., 4×4, 8×8, 12×12, 16×16, 20×20).

5. **Evaluate Results**  
   For each grid size, the notebook displays:
   - Compressed image (RGB)
   - Cluster position map (BMU indices)
   - SOM codebook grid
   - Reconstructed bands
   - MSE value

6. **Analyze MSE Trend**  
   View the final plot showing MSE vs. SOM grid size.

---

## Key Code Components

- **SOM Class**  
  Includes initialization, training, winner selection, and pixel mapping.

- **Image Utilities**  
  Load, reshape, reconstruct, and compress multispectral images.

- **Visualization**  
  Uses `matplotlib` for all visual plots.

- **MSE Calculation**  
  Quantifies reconstruction quality.

---

## Example Results

| SOM Grid Size | MSE     |
|---------------|---------|
| 4x4           | 0.00082 |
| 8x8           | 0.00064 |
| 12x12         | 0.00061 |
| 16x16         | 0.00041 |
| 20x20         | 0.00058 |

> Larger grid sizes generally result in better reconstruction (lower MSE), but with diminishing returns and higher computational cost.

---

## How to Run

1. Open `SOM_GNR602_Project.ipynb` in **Jupyter Notebook**.
2. Update file paths according to your environment.
3. Run all cells sequentially.
4. View the output images and plots inline.

---

## Customization

- Change the input TIFF files or number of bands (e.g., for other sensors).
- Tune SOM parameters (`learning_rate`, `max_iter`, `grid_size`) to experiment.
- Extend the codebase to test other clustering or compression techniques.

---
