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
3.**Create a virtual environment**
   python -m venv env

4. **Activate the virtual environment**

   On Windows:
   .\env\Scripts\activate
   On macOS and Linux:
   source env/bin/activate
5.**Install dependencies**
   pip install -r requirements.txt
6.Download the Segment Anything Model (SAM) checkpoint:
   wget https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth

##Usage
1.**Run the Streamlit app**
   streamlit run app.py
2.**Interact with the app**

3.**Upload an image file in JPEG, JPG, or PNG format**

Click on the "Original" button to view the uploaded image.
Click on the image to select the point where you want the background removed.
Hit the "Remove background" button to generate the processed image without the background.
API Deployment (Optional)
The app is configured to work with a Modelbit API for background removal.
Endpoint: use your api from modelbit
Input: Encoded image in Base64 format and X/Y coordinates.
Output: Processed image with transparent background.

##Troubleshooting
Ensure the SAM checkpoint is downloaded and in the correct path.
Check if all dependencies are properly installed.
##License
This project is licensed under the MIT License. See the LICENSE file for details.
