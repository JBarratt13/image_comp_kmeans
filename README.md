# image_comp_kmeans
# Image Compression with K-Means Clustering

Compresses images by reducing the number of unique colours using a from-scratch K-means clustering implementation in Python — no sklearn, just NumPy, OpenCV, and matplotlib.

## How It Works

1. The image is loaded with OpenCV and pixel values are normalised to [0, 1]
2. Pixels are flattened into a 2D matrix of RGB values
3. K-means is run for 10 iterations — each pixel is assigned to its nearest centroid using Euclidean distance
4. Centroids are recomputed as the mean of all assigned pixels each iteration
5. The compressed image is reconstructed by replacing each pixel with its centroid colour and saved to disk

## Usage

```bash
pip install numpy opencv-python matplotlib
python main
```

You'll be prompted to enter the number of colours (e.g. `16`). The compressed image is saved as `compressed_16_colors.png`.

## Example

| Colours | Effect |
|---------|--------|
| 16 | Very close to original, smaller file |
| 8  | Noticeable posterisation |
| 2  | Binary colour reduction |

## Project Structure
image_comp_kmeans/
├── main # Full K-means compression script
└── README.md


## What This Demonstrates

- Manual implementation of K-means (no ML library)
- Understanding of centroid initialisation and convergence
- Image representation as a matrix of RGB vectors
- Unsupervised learning applied to a real computer vision task

## Tech Stack

Python · NumPy · OpenCV · matplotlib
