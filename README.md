# Image-Caption-Generator
This repository contains code for an image caption generator using a combination of a pre-trained VGG16 model and a Long Short-Term Memory (LSTM) network. The model takes an image as input and generates a descriptive caption.
## Dependencies
Make sure you have the following dependencies installed:
<br>os
<br>pickle
<br>numpy
<br>tqdm
<br>keras
<br>tensorflow
<br>PIL (Pillow)
<br>matplotlib

You can install these dependencies using the following command:
```bash
pip install os pickle numpy tqdm keras tensorflow Pillow matplotlib
```
## Usage
### Download Pre-trained VGG16 Model Weights
The code utilizes the VGG16 model, and you need to download the pre-trained weights. You can do this by running the following command:
```python
from tensorflow.keras.applications.vgg16 import VGG16
model = VGG16()
```
### Prepare Image Data
Place your images in the 'Images' directory. The code expects images to be preprocessed and resized to (224, 224). The provided code snippet extracts features from these images using the VGG16 model and stores them in a pickle file (features.pkl).
### Prepare Caption Data
Create a text file (captions.txt) containing image captions. Each line in the file should follow the format: image_id, caption. The code will preprocess and clean the captions.
