# Final Project: Flower Classification Application
<i>Kyle Gallagher | MSDS462 Computer Vision </i>
•	Overview
•	Data Sources
•	Model
•	Application
•	Results and Next Steps

## Overview:
My wife and I love taking walks through our neighborhood. Living in an urban environment we see a lot of really cool flowers and plants along the sidewalk. I constantly am asking my wife what a certain flower an am met with the common “How should I know” response.
This struck me as a perfect Computer Vision application. My approach to this was very simple. Find a flower dataset, apply a pretrained model with transfer learning to predict the type of flower, then place it into a simple Android skeleton app that could be loaded onto my phone. 
Data Sources:
To test my prototype I trained my model on a simple flower dataset from TensorFlow that consists of 5 classes: Dandelions, Daisies, Sunflowers, Tulips, and Roses. 
After getting the prototype to work I searched for another more expansive dataset. I found a good one from the University of Oxford that has 17 different classes that I used for the latest version of my model: 
•	bluebell
•	buttercup
•	coltsfoot
•	cowslip
•	crocus
•	daffodil
•	daisy
•	dandelion
•	fritillary
•	iris
•	lilyvalley
•	pansy
•	snowdrop
•	sunflower
•	tigerlily
•	tulip
•	windflower


## Model:
As mentioned in the overview I used transfer learning with a pretrained TensorFlow model. TensorFlow has a great library called ModelMaker that has pretrained models specifically tuned to certain tasks such as object detection or audio classification. The models are pretrained, include preprocessing such as normalizing pixels, and generally allow users to quickly build on-device ML applications. With just a few lines of code you can train an accurate model, test it, and export the tflite file with metadata that has been quantized to reduce size and possibly increase the speed on your device.
I chose this route both to explore this feature I hadn’t used before and to aide in developing a quick proof of concept.  ModelMaker is a great way to test out a use case for viability without spending hours coding complex models. 

## Android Application:
One sticking point I identified early on was the complete lack of experience I have with app development for mobile devices. Luckily when searching the internet I was able to find precompiled code that can be used to build a simple skeleton Android app. It isn’t anything fancy but by cloning this repository I was able to drop my model into it and move it to my device using Android Development Studio.

## Results and Next Steps:
The app works but accuracy isn’t as great as I’d like it to be. This is due to the limitations of my dataset. Certain flowers are only in one color in the data so when the app sees a purple tulip it thinks it’s an iris since most of the irises are purple. 
While working on this project I read up on others attempting this application. I quickly found this was harder than expected due to the fact that flowers have high intra-species variance and low inter-species variance. Different species can look similar and flowers of the same species can vary widely in color and size.
The best means of tackling this is with more data as well as applying some image augmentation (perhaps incorporating black and white images to reduce the dependency on color). 
