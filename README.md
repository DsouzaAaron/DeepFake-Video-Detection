# DeepFake-Video-Detection
DeepFake Video Detection Project
## About

In this project we propose different methods to detect Face Swapped DeepFake Videos.
<html>  
1. CNN Models<br>
  <p>
First we extract videoframes from videos, then we extract face from the frame and simultaneously apply pretrained CNN models to predict whether the given frame is REAL or FAKE. If total number of FAKE frames exceed a certain threshold, we predict that the input video is FAKE otherewise REAL.</p>
    Different CNN models used,
   <ul>
     <li>EfficientNetB0</li>
     <li>ResNet50</li>
     <li>MesoNet</li>
  </ul>
 <p>Here for EfficientNet and ResNet we used imagenet weights and for MesoNet we used pretrained DeepFake detection weights available online.</p>
  
2. Combination of CNN and RNN models<br>
  <p>
 Even though the previous approach was direct, the results were not satisfactory. Hence we moved on to this approach.
 In this approach we first select a few frames from videos (processing all the frames require high computational resources and consumes a lot of time) and  then extract face from the frame and use a CNN model to extract facial features. We then concatenate the facial features of all the frames and pass it to RNN model, which  predicts whether the video was REAL or FAKE.</p>
 
 For the CNN model we experimented with
  <ul>
    <li>InceptionNet</li>
    <li>EfficientNetB0</li>
  </ul>

 For the RNN modek we used with
  <ul>
    <li>GRU</li>
  </ul>
 
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
