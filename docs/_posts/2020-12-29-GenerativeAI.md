---
layout: post
title:  "Generative AI"
date:   2020-12-29 
categories: blog
post_icon : "/assets/images/optimus_transformer.jpg"
---

<img src="/assets/images/optimus_transformer.jpg" style="width: auto; height: 350px;">

# TL;DR
Generative AI is all the rage today. This however has a history where ML tasks were more narrowly defined using deep neural network. I have been following this space since 2017 and sharing my learning with friends and colleagues. Here is smattering of notebooks from the past.

## [Deep Learning From Above](https://github.com/pankajksingh/play/blob/main/src/nabu/DeepLearningFromAbove.ipynb)
I was inspired to choose the title after listening to the very funny talk on  YouTube by Feynman titled [Los Alamos From Below](https://calteches.library.caltech.edu/34/3/FeynmanLosAlamos.htm). My intent was to understand high level concepts of deep learning. Here I start with a cluster of points in a 2D space. I first produce the best fit line using linear algebra. I then recreate the same line using Pytorch's nn.module. This illustrates the ML training loop with forward and backward passes that aim to reduce the training loss and arriving at the weights characterizing the line in terms of intercept and slope. The deep learning method is more general and can be applied widely for other functions.

## [Transfer Learning](https://github.com/pankajksingh/play/blob/main/src/transfer-learning/TransferLearning_FastAI.ipynb)
I was inspired by Jeremy Howard's [FastAI](https://www.fast.ai/) offering. In this notebook I explore the FastAI deep learning library. He built a layered architecture which looks like traditional software consisting of high level, mid level and lower level apis. For a simple use case, we can build a solution using the highest layer. I illustrate tansfer learning where we start with a pretained classifier model and fine tune it for sentiment analysis using FastAI learner class.

## [Convolutional Neural Network](https://github.com/pankajksingh/play/blob/main/src/cnn/nn_tutorial_cnn.ipynb)
This notebook explores some of the inspirations behind deep neural network in general and CNN in particular. We review the similarities between biological neurons and artificial neurorns. ANN(Artificial neural network) is built by interconnecting very many artificial neurons. We describe [Hubel and Weisel experiment](https://historyofinformation.com/detail.php?entryid=4726) which inspired filters and hierarchichal abstractions in CNNs. Later [Zeiler and Fergus](https://arxiv.org/pdf/1311.2901) deepened our understanding of what goes behind a CNN. We use Pytorch to illustrate use of CNN to identify handwritten digits using the famous MNIST dataset.

## [Sequence Modeling](https://github.com/pankajksingh/play/blob/main/src/fseq/iitk/Seq2Seq.ipynb)
This is close to my heart. During pandemic, my school colleague started a talk series where folks from 97 IIT Kanpur batch will be sharing their learnings to batch mates. Everyone in the audience had a technical bent but life had taken them into different directions. I started with the value proposition where ML can be thought of a function approximator , thus allowing us to map any input x to output y. I introduce the ML training loop. Then I use [fairseq](https://github.com/facebookresearch/fairseq) to learn an add function. This learns to do a string translation of numbers into their sum. For e.g. given 2+5, it will produce 7 without doing the normal addition. It is surprising how accurate it gets. This also shows that it will occasionally hallucinate as it is not building any logical model to do the addition.

## [Chat GPT](https://github.com/pankajksingh/play/blob/main/src/chatgpt/ChatGPT.ipynb)
This is shortly after ChatGPT burst into the scene and there was strong desire to understand the magic behind its phenomenal success. I scoured the web and found [HuggingFace](http://huggingface.co/) to be a great resource. Lewis Tunstall from Hugging Face released a book Natural Language Processing with [Transformers Book](https://transformersbook.com/) around the same time. I used Hugging Face transformer's library to illustrate various tasks. I then covered the history of GPT by levaraging Lewis's work. This covered the notion of Attention and the Transformer architecture. I also covered post-training via RLHF, a key ingredient of the quality at that time. Finally I showcased some samples that felt like magic.









