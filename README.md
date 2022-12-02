# DeepFake-Video-Detection
DeepFake Video Detection Project

In this project we propose different methods to detect Face Swapped DeepFake Videos.

1. CNN Models
First we extract videoframes from videos, then we extract face from the frame and simultaneously apply pretrained CNN models to predict whether the given frame is REAL or FAKE. If total number of FAKE frames exceed a certain threshold, we predict that the input video is FAKE otherewise REAL.
Different CNN models used,
  i. EfficientNetB0
  ii. ResNet50
  iii. MesoNet
 Here for EfficientNet and ResNet we used imagenet weights and for MesoNet we used pretrained DeepFake detection weights available online.
 
 2. Combination of CNN and RNN models
 

Combination of CNN and RNN model is used to detect Fake Videos.
We achieved a test accuracy ~85% on sample DFDC dataset 

To run this code first run this command 
### pip install -r requirements.txt
Run main.py file in the deploy folder
### python main.py

Make sure the required packages are installed, and it is preferred to run on GPU.
The results are given in about a minute for a 10 second 30fps video.
