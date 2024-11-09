Background Remover App
The Background Remover App is a Streamlit-based application that allows users to upload images, click on specific coordinates in the image, and remove the background around the selected point. Using Facebook's Segment Anything Model (SAM), this app achieves precise background removal with the chosen coordinates.

Features
Image Upload: Upload an image in JPEG, JPG, or PNG format.
Coordinate Selection: Select a point within the image to identify the subject and remove the surrounding background.
Background Removal: Leverages deep learning-based segmentation to remove the background around the selected subject.
Smooth Display: Real-time background removal and image rendering within the app.
Prerequisites
Python 3.8+

Clone the repository:

bash
Copy code
git clone <repo-url>
Create a virtual environment:

bash
Copy code
python -m venv env
Activate the virtual environment:

On Windows:
bash
Copy code
.\env\Scripts\activate
On macOS and Linux:
bash
Copy code
source env/bin/activate
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Download the Segment Anything Model (SAM) checkpoint:

bash
Copy code
wget https://dl.fbaipublicfiles.com/segment_anything/sam_vit_b_01ec64.pth
Usage
Run the Streamlit app:

bash
Copy code
streamlit run app.py
Interact with the app:

Upload an image file in JPEG, JPG, or PNG format.
Click on the "Original" button to view the uploaded image.
Click on the image to select the point where you want the background removed.
Hit the "Remove background" button to generate the processed image without the background.
API Deployment (Optional)
The app is configured to work with a Modelbit API for background removal.

Endpoint: https://ussayedshakeelabbasi.us-east-2.aws.modelbit.com/v1/remove_background/latest
Input: Encoded image in Base64 format and X/Y coordinates.
Output: Processed image with transparent background.
Example Code Snippet for API Usage
To remove the background using the deployed Modelbit API:

python
Copy code
import base64
import requests

api_endpoint = "https://ussayedshakeelabbasi.us-east-2.aws.modelbit.com/v1/remove_background/latest"
image_path = './test.png'

# Load and encode the image
with open(image_path, 'rb') as img_file:
    image_data = img_file.read()
image_base64 = base64.b64encode(image_data).decode('utf-8')

# Set coordinates (replace with actual values)
x, y = 528, 606
api_data = {"data": [image_base64, x, y]}

# Send request to API
response = requests.post(api_endpoint, json=api_data)
result_image_base64 = response.json()['data']

# Decode and save the result image
result_image_data = base64.b64decode(result_image_base64)
with open("result_image.png", "wb") as img_file:
    img_file.write(result_image_data)
Troubleshooting
Ensure the SAM checkpoint is downloaded and in the correct path.
Check if all dependencies are properly installed.
License
This project is licensed under the MIT License. See the LICENSE file for details.






