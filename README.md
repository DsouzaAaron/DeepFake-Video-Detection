# DeepFake-Video-Detection
DeepFake Video Detection Project
## About

In this project we propose different methods to detect Face Swapped DeepFake Videos.

1. CNN Models
First we extract videoframes from videos, then we extract face from the frame and simultaneously apply pretrained CNN models to predict whether the given frame is REAL or FAKE. If total number of FAKE frames exceed a certain threshold, we predict that the input video is FAKE otherewise REAL.
Different CNN models used,
  ..* i. EfficientNetB0
  ..* ii. ResNet50
  ..* iii. MesoNet
 Here for EfficientNet and ResNet we used imagenet weights and for MesoNet we used pretrained DeepFake detection weights available online.
 
 2. Combination of CNN and RNN models
 Even though the previous approach was direct, the results were not satisfactory. Hence we moved on to this approach.
 In this approach we first select a few frames from videos (processing all the frames require high computational resources and consumes a lot of time) and  then extract face from the frame and use a CNN model to extract facial features. We then concatenate the facial features of all the frames and pass it to RNN model, which  predicts whether the video was REAL or FAKE.
 
 For the CNN model we experimented with
 ..* i. InceptionNet
 ..* ii. EfficientNetB0
 
 For the RNN modek we used with
 ..* i. GRU
 
 The best model we obtained was InceptionNet + GRU archtiecture. This model is used for deployment.

## Running Code

Combination of CNN and RNN model is used to detect Fake Videos.
We achieved a test accuracy ~85% on sample DFDC dataset 

To run this code first run this command 
### pip install -r requirements.txt
Run main.py file in the deploy folder
### python main.py

Make sure the required packages are installed, and it is preferred to run on GPU.
The results are given in about a minute for a 10 second 30fps video.
