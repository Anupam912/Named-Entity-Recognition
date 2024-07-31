# Recurrent neural networks for   named entity recognition in TensorFlow

This repository contains a simple named entity recognition.

## Requirements

- [Tensorflow=1.2.0](https://github.com/tensorflow/tensorflow)

## Model

The model is a birectional LSTM neural network with a CRF layer. Sequence of characters are projected into sequence of dense vectors, and concated with extra features as the inputs of recurrent layer, here we employ one hot vectors representing word boundary features for illustration. The recurrent layer is a bidirectional LSTM layer, outputs of forward and backword vectors are concated and projected to score of each tag. A CRF layer is used to overcome label-bias problem.

Our model is similar to the state-of-the-art   named entity recognition model proposed in Character-Based LSTM-CRF with Radical-Level Features for   Named Entity Recognition.

## Basic Usage

### Default parameters

- batch size: 20
- gradient clip: 5
- embedding size: 100
- optimizer: Adam
- dropout rate: 0.5
- learning rate: 0.001

Word vectors are trained with gensim version of word2vec

### Train the model with default parameters

```shell
python3 main.py --train=True --clean=True
```

### Online evaluate

```shell
python3 main.py
```
