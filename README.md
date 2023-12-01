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
### Train the model
The code then tokenizes the captions, prepares the data, and trains the model. The model architecture consists of a combination of a Dense layer and an LSTM layer.
```python
model.fit(generator, epochs=20, steps_per_epoch=steps, verbose=1)
```
### Evaluate the model
After training, the model is saved as 'best_model.h5'. You can load this model for evaluation.
```python
model = keras.models.load_model('best_model.h5')
```
### Generate Captions 
Use the 'Generate_caption' function to generate captions for a given image.
```python
generate_caption("your_image.jpg")
```
The function loads the image, displays actual captions, predicts a caption, and displays the image with the predicted caption.
## Notes
<br>The model architecture and training parameters can be adjusted based on your specific requirements.
<br>Ensure that you have the necessary permissions to access and modify files in the 'Images' directory.
<br>Feel free to explore and modify the code to suit your needs. Happy captioning! 📸📝
