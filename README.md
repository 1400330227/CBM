# Concept Bottleneck Models (under construction)

This repository contains code and scripts for the following paper:

> Concept Bottleneck Models
>
> Pang Wei Koh\*, Thao Nguyen\*, Yew Siang Tang\*, Stephen Mussmann, Emma Pierson, Been Kim, and Percy Liang
>
> ICML 2020

The experiments use the following datasets:
- [NIH Osteoarthritis Initiative (OAI)](https://nda.nih.gov/oai/)
- [Caltech-UCSD Birds 200 (CUB)](http://www.vision.caltech.edu/visipedia/CUB-200.html)

The NIH Osteoarthritis Initiative (OAI) dataset requires an application for data access, so we are unable to provide the raw data here. 
We focus instead on scripts replicating our results on CUB, which is a public dataset.

## Abstract
We seek to learn models that we can interact with using high-level concepts:
would the model predict severe arthritis if it thinks there is a bone spur in the x-ray?
State-of-the-art models today do not typically support the manipulation of concepts like "the existence of bone spurs",
as they are trained end-to-end to go directly from raw input (e.g., pixels) to output (e.g., arthritis severity).
We revisit the classic idea of first predicting concepts that are provided at training time,
and then using these concepts to predict the label.
By construction, we can intervene on these _concept bottleneck models_
by editing their predicted concept values and propagating these changes to the final prediction.
On x-ray grading and bird identification, concept bottleneck models achieve competitive accuracy with standard end-to-end models,
while enabling interpretation in terms of high-level clinical concepts ("bone spurs") or bird attributes ("wing color").
These models also allow for richer human-model interaction: accuracy improves significantly if we can correct model mistakes on concepts at test time.