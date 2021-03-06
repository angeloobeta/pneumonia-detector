# Pneumonia Detector
Side Project for the Deep Learning with Pytorch - Udacity challenge

Pneumonia   is one of the hardest disease to detect especially in it's first stage 
So our goal was to make an easy to use application that can predict if someone
has Pneumonia or not given its chest x-ray.
![example chest x-ray](/imgs/example-chest-xray.jpg)

## Steps
- First, we trained a neural network to classify chest x-rays (Pneumonia/Normal), and we obtained 99% of accuracy when we tested on data that has never seen before so we can say that our model will do a great job in the classification of any X-ray

  The training was done on [Kaggle](https://www.kaggle.com/yasserlatreche/pneumonia-99-accuracy-using-densenet121) but you can also find a copy of the notebook under the notebooks sub directory
  
- Then we built a RESTful API around that model so other applications can use this service. The RESTful API code is under the server sub directory

- Finally we built a web application that uses the API and make it's usage really easy, the source code is under the webapp sub directory

  You love terminals ? there is also a CLI utility for you, check the is_pneumo.py script

## How to use it?

#### The Web Application
We made a simple web application to load your Chest X-ray and see the reasults

The first step is to load the image using the 'Upload your X-ray ' button 
![main page](/imgs/Main-page.png)

and the Second step is to see the results by clicking on the  'See the Results' Button
![Results](/imgs/Result.png)

#### The CLI utility
First, you need to make sure that there is an API available before using the CLI utility (is_pneumo.py). At the time of writing this, the API was hosted on http://130.211.108.207:3000/pred

Then you need to setup the new IP (or hopefully a domain name) of the API if it has changed by replacing the API_URL variable

The last step is to run it:
```
$ ./is_pneumo.py my_chest_xray.jpg
[+] It's NORMAL with a 0.996976 probability
[+] It's PNEUMONIA with a 0.003024 probability
```
