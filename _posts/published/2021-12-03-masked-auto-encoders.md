---
title: Masked Autoencoders are Scalable Vision Learners
layout: post
# post-image: "https://raw.githubusercontent.com/thedevslot/WhatATheme/master/assets/images/What%20is%20Jekyll%20and%20How%20to%20use%20it.png?token=AHMQUELVG36IDSA4SZEZ5P26Z64IW"
description: Impressions on this groundbreaking paper.

tags:
- research
- technology
- AI
---

# How I heard about the paper

Walking with a friend in Paris we talked about AI. Between other things, his research on self-supervised learning. He warned me that a great paper was going to appear, and it did. [Here](https://arxiv.org/pdf/2111.06377.pdf) you have it. 

# Transformer moment in computer vision?
A key moment in NLP (natural language processing) was the introduction of the transformer architecture, a new artificial neural network design that showed impressive results. The year after its introduction, most of the papers were something like "we used transformers for this problem and we were better". 

This is an example of a groundbreaking moment. In NLP, one uses transformers to predict some hidden part of the input. In this way one does not need annotated data, as the "annotated data" are the words that were hidden. Although not so long ago the transformer architecture was transferred into vision, we were not using the same masking principle to learn from unlabeled data. But this paper introduces this principle.

What is interesting is that they achieve top performance in ImageNet, presumably the most classical and competitive computer vision benchmark. But not only that, they also are top performers in transfer learning to different tasks, like detection, classification or segmentaiton over COCO database. The fact that such a simple method can perform very well in such a large variety of domains is awesome.

# How does it work?

The main ingredients of this method are i) Vision Transformers (ViT), ii) masking a large proportion (+70%) of the input image patches and iii) an autoencoder architecture, in the sense of going to a latent space and then reconstructing the input image.

Some other details include that the patches are shuffled and only the non-masked patches are passed to the encoder, whereas all patches are passed to the decoder. The evaluation is done both by checking the trained linear combination of the extracted features and the trained nonlinear combination of the extracted features. They are stronger in the second case.

We will see if this enjoys rapid adoption or is not as groundbreaking as it promises to be (even inside the paper).

