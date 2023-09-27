# Incorporating fine grained/additional labels with custom loss function in Google Contrail competition

## The competition

_Google Research - Identify Contrails to Reduce Global Warming_ was hosted on Kaggle and tasked competitors to create a ML model which creates a pixel mask marking contrails on sattelite data.

![contrails](https://storage.googleapis.com/kaggle-media/competitions/Google-Contrails/waterdroplets.png)

### Labels

One of the interesting features of the given data was that besides a ground truth mask, additionally the individual masks of each human annotator was given. The ground truth was computed from the individual masks.

> Ground truth was determined by (generally) 4+ different labelers annotating each image. Pixels were considered a contrail when >50% of the labelers annotated it as such. Individual annotations (human_individual_masks.npy) as well as the aggregated ground truth annotations (human_pixel_masks.npy) are included in the training data. The validation data only includes the aggregated ground truth annotations.

![masks](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F59561%2F590a0bc76044a4ceb71368cf3b62412e%2Fcontrails_600.png?generation=1683669162469942&alt=media)

### Evaluation metric

> This competition is evaluated on the global Dice coefficient.

## My experiment

My goal was to find good hyperparameters for a custom loss function which weighs (i) A F-beta-Score of the ground truth mask with (ii) A F-beta-Score of the Union of the individual masks.

**My intuition** was that choosing the betas such that (i)slightly penalizing false positives on the ground truth mask and (ii) penalizing false negatives more on the union of all individual masks should lead to a better result than just using a F-1-Score(/Dice Score) on the ground truth as basis for the loss function.

### Individual masks

# Google Research - Identify Contrails to Reduce Global Warming

## Overview

## Evaluation

## Different Annotations
