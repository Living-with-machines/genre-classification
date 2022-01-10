# Predicting Genre with Machine Learning

[![Jupyter Book Badge](https://raw.githubusercontent.com/executablebooks/jupyter-book/ec23010e233013c3c2e5c35257d044664829a782/docs/images/badge.svg)](https://living-with-machines.github.io/genre-classification/)
[![DOI](https://zenodo.org/badge/436688599.svg)](https://zenodo.org/badge/latestdoi/436688599)


**Note** This material is a work in progress. If you have any feedback or suggestions please [open an issue](https://github.com/Living-with-machines/genre-classification/issues/new).


[<img src="https://user-images.githubusercontent.com/8995957/148814318-f87a3851-21de-45f2-8dfa-e7aec8a2a7dd.png">](https://living-with-machines.github.io/genre-classification/intro.html)


There is a growing interest in using Machine Learning to automatically produce metadata for GLAM (Galleries, Libraries, Archives and Museums) collections. This repository contains the source material for a Jupyter book that moves through the steps of developing a machine learning model to classify book titles into 'crude' genres (fiction or non-fiction). In particular, we work with the British Library's ["Microsoft Digitised Books"](https://www.bl.uk/collection-guides/digitised-printed-books) collection to automatically generate metadata for ~49,455 titles. 

The [Jupyter Book](https://jupyterbook.org/) aims to give an overview of the broader pipeline involved in creating machine learning models, i.e. not just showing the model training process but steps before and after this. Topics covered in the material include: 

- exploring our training data against the entire corpus and assessing the 'representativeness' of our digitised collection
- training an initial baseline model
- assessing weaknesses in our model 
- using weak supervision to create more training data
- discussion of how to share models and data

We use several Python machine learning libraries in the notebooks:

- [fastai](https://docs.fast.ai/)
- [🤗 Transformers](https://huggingface.co/docs/transformers/index) / [Blurr](https://github.com/ohmeow/blurr)
- [Snorkel](https://www.snorkel.org/)

While we aim to give an overview of the steps involved in training a machine learning model, we don't aim to introduce machine learning or Natural Language Processing fully.

## Other outputs

As part of this work we also share:

- the intial training data: https://doi.org/10.23636/BKHQ-0312 
- the baseline model: https://zenodo.org/record/5245175 
- the improved model: https://huggingface.co/BritishLibraryLabs/bl-books-genre 
