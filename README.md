# Face Emotion Recognition

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#purpose-of-project">Purpose of Project</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#architecture">Architecture</a></li>
    <li><a href="#technologies">Technologies</a></li>
    <li><a href="#how-to-run">How to run</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## Purpose of Project

* Train a model to classify human's face emotion (happiness, sadness, anger, fear, disgust, surprise and neutral)
* Learn about PyTorch

## About

This is a PyTorch implementation of research paper, [Deep-Emotion](https://arxiv.org/abs/1902.01019)

## Architecture

* An end-to-end deep learning framework, based on Attentional Convolutional Network
* Attention mechanism is added through spatial transformer network


## Technologies

* Language: Python
* Framework: PyTorch

## How to run

### Prerequisites

Required Libraries:
* pytorch >= 1.1.0
* torchvision ==0.5.0
* opencv
* tqdm
* PIL

### Data preparation

Download the dataset from [Kaggle](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data), and decompress ```train.csv``` and ```test.csv``` into ```./data``` folder.

### Setup the dataset
```
python main.py [-s [True]] [-d [data_path]]

--setup                 Setup the dataset for the first time
--data                  Data folder that contains data files
```

### To train the model
```
python main.py  [-t] [--data [data_path]] [--hparams [hyperparams]]
                                [--epochs] [--learning_rate] [--batch_size]

--data                  Data folder that contains training and validation files
--train                 True when training
--hparams               True when changing the hyperparameters
--epochs                Number of epochs
--learning_rate         Learning rate value
--batch_size            Training/validation batch size
```

### To validate the model
A small bug where it said that `KeyError(key) no key name 'emotion'` can be fixed by adding `',emotion,'` before `'pixel'` in `test.csv`
```
python visualize.py [-t] [-c] [--data [data_path]] [--model [model_path]]

--data                  Data folder that contains test images and test CSV file
--model                 Path to pretrained model
--test_cc               Calculate the test accuracy
--cam                   Test the model in real-time with webcam connect via USB
```

## Acknowledgments

* This project was recreate of and update from [this repo](https://github.com/omarsayed7/Deep-Emotion).
* Youtube Tutorial: [video](https://www.youtube.com/watch?v=yN7qfBhfGqs)
* How to Implement Spatial Transformer Network in PyTorch: [doc](https://pytorch.org/tutorials/intermediate/spatial_transformer_tutorial.html)
