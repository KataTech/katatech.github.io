---
layout: page
title: OTIST
permalink: /research/ot-ist
description: an optimal transport approach to independent subnetwork training
nav: false
horizontal: false
---

### Transfer Learning and Domain Adaptation

In practice, machine learning systems are often trained and applied to datasets that come from similar, but not exact distributions. Most of the time, these differences may be attributed to randomness within the generating process. However, sometimes these differences come from systematic differences between the generating process of the training data and the real-world data. Examples of these include: 
- Applying a voice-to-command system trained on Americans to the British population
- Applying an image classifier trained on pictures taken by high-quality cameras to those taken by lower quality cameras
- Applying a facial recognition system trained on lighter skin complexity to populations with darker skin complexity

Failures to account for these differences in source and target data distributions led to many headlines, ranging from high-publicity scandals such as [Facebook's facial recognition software](..) to subtle inconveniences such as [..](..). These news headlines led to inventions of research areas such as ML Robustness and Interpretable Machine Learning. 

One may raise a few questions... 
1. Why don't we just train the model on the data that we expect to get? 
2. Why can't we train with perturbations of input data that we expect? 

To address (1), we often don't have access to the test data and cannot anticipate all the transformations between the input that we have and the input we *may* receive. As for (2), while this approach works well for anticipated perturbations such as image blurs or rotations, the possible types of perturbations are usually too many for us to manually try.

The term [Domain Adaptation](...) describes this phenomenon, and [Transfer Learning](...) describes the model training approach where we conduct fine-tuning on pre-trained models to adopt it to a new domain that is slightly different from the original training setting. Hence, these two terms are very connected. 