# Background Remover App

The **Background Remover App** is a Streamlit-based application that allows users to upload images, select specific coordinates in the image, and remove the background around the selected point. Using Facebook's **Segment Anything Model (SAM)**, this app achieves precise background removal with the chosen coordinates.

## Features

- **Image Upload:** Upload an image in JPEG, JPG, or PNG format.
- **Coordinate Selection:** Click a point within the image to select the subject and remove the surrounding background.
- **Background Removal:** Uses a deep learning-based segmentation model for accurate background removal around the selected subject.
- **Real-Time Display:** Real-time background removal and image rendering within the app.

## Prerequisites

1. **Python 3.8+**
2. **Clone the Repository**
   ```bash
   git clone <repo-url>
