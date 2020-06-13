# ASL-recogniser
American Sign language translator

The goal of this project was to build a sign language translator. That is, an application capable of interpreting the actions made by one user in video form, and translating that to text. I used the American Sign language for this purpose, to interpret alphabets.

### Dataset source:
  https://www.kaggle.com/grassknoted/asl-alphabet
  
### Technology used:
Python, openCV (for getting input video and preprocessing it), Tensorflow (for the convolution model)
  
### How it works:
1. Train and save a convolution mode to recognise alphabets using train dataset.
2. Get video feed from webcam and preprocess each frame to remove backgroung and threshold the image, so that the hand action is highlighted
3. Pass this preprocessed image to the model to predict the action
4. Display the prediction text on screen along with video
  
The jupyter notebook contains the code for final model used and F1 scores for various classes.
The asl_abc video depict the model in action, on an youtube video (https://www.youtube.com/watch?v=pDfnf96qz_4)
Refered code (https://www.pyimagesearch.com/2019/07/15/video-classification-with-keras-and-deep-learning/, https://gogul.dev/software/hand-gesture-recognition-p1)

## Results: 
  The convolution model achieved 99% accuracy, while the test accuracy was lower, around 60%. On analysing the cause I found that, the dataset used to train the model was perfectly tresholded, to classify the hand action from the background, and my method to threshold the live camera feed, was not as accurate. This lead to a significant drop in perfoemance.
  
### Lesson learnt: 
Make sure the preprocessing in train dataset matches as much as possible to the test dataset
