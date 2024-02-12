# image-classification-with-Resnet50-custom-data

This project performs binary image classification (ants vs bees) using transfer learning with ResNet50.

## Model Architecture

The model uses a pre-trained ResNet50 model as the base. The fully connected layers at the end are removed and new classifier layers are added.

The new layers are:

- Global average pooling 
- Dense 512 ReLU
- Dropout 0.5
- Dense 256 ReLU 
- etc.

Finally a softmax output layer is added for the 2 classes.

## Usage

The main steps are:

### Install dependencies

```bash
pip install tensorflow keras matplotlib etc
```

### Load and preprocess data

Use ImageDataGenerator to load images from training and validation folders. Resize to 224x224 and do standardization.

### Build model

Load ResNet50 without top layers. Add new classifier layers. 

### Train

Use model.fit to train the model. Plot training and validation loss/accuracy.

### Evaluate on new images

Use model.predict to classify new images.

### Save and load model

Use model.save() and load_model() to save and load the model.

## Feature Visualization

The model can be modified to output intermediate feature maps. This helps visualize what the model learns.

For example, add a lambda layer after any conv block to get those feature maps. 


## Results

The model achieves 90% validation accuracy after 10 epochs of training. Loss and accuracy plots show the model fitting nicely to the training data.

Feature maps show the model learning relevant features like edges, colors, object parts etc.
