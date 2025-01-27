This is a slight modification of cw75's fork to make it a working module in 2022.

### Changes made
- Add model download module to package and fix some prompts
- Fix setup.py requirements

### ------ Update September 2018 ------
It's been a year since TorchMoji and DeepMoji were released. We're trying to understand how it's being used such that we can make improvements and design better models in the future. 

You can help us achieve this by answering this [4-question Google Form](https://docs.google.com/forms/d/e/1FAIpQLSe1h4NSQD30YM8dsbJQEnki-02_9KVQD34qgP9to0bwAHBvBA/viewform "DeepMoji Google Form"). Thanks for your support!

# 😇 TorchMoji

> **Read our blog post about the implementation process [here](https://medium.com/huggingface/understanding-emotions-from-keras-to-pytorch-3ccb61d5a983).**

TorchMoji is a [pyTorch](http://pytorch.org/) implementation of the [DeepMoji](https://github.com/bfelbo/DeepMoji) model developped by Bjarke Felbo, Alan Mislove, Anders Søgaard, Iyad Rahwan and Sune Lehmann.

This model trained on 1.2 billion tweets with emojis to understand how language is used to express emotions. Through transfer learning the model can obtain state-of-the-art performance on many emotion-related text modeling tasks.

Try the online demo of DeepMoji [http://deepmoji.mit.edu](http://deepmoji.mit.edu/)! See the [paper](https://arxiv.org/abs/1708.00524), [blog post](https://medium.com/@bjarkefelbo/what-can-we-learn-from-emojis-6beb165a5ea0) or [FAQ](https://www.media.mit.edu/projects/deepmoji/overview/) for more details.

## Overview
* [torchmoji/](torchmoji) contains all the underlying code needed to convert a dataset to the vocabulary and use the model.
* [scripts/](scripts) contains code for processing and analysing datasets to reproduce results in the paper.
* [model/](model) contains the pretrained model and vocabulary.
* [data/](data) contains raw and processed datasets that we include in this repository for testing.

Please consider citing the [paper](https://arxiv.org/abs/1708.00524) of DeepMoji if you use the model or code (see below for citation).

## Installation

We assume that you're using [Python 3.8 >=](https://www.python.org/downloads/) with [pip](https://pip.pypa.io/en/stable/installing/) installed.

Install the package with pip:
```bash
pip install git+https://github.com/themysticsavages/torchMoji
```

Or do it manually:
```bash
git clone https://github.com/themysticsavages/torchMoji
cd torchMoji
python3 setup.py install
```

Then, run the download script to downloads the pretrained torchMoji weights (~85MB) from [here](https://www.dropbox.com/s/q8lax9ary32c7t9/pytorch_model.bin?dl=0) and put them in the model/ directory:

```bash
python scripts/download_weights.py
```

## Disclaimer
This code has been tested to work with Python 2.7 and 3.5 on Ubuntu 16.04 and macOS Sierra machines. It has not been optimized for efficiency, but should be fast enough for most purposes. We do not give any guarantees that there are no bugs - use the code on your own responsibility!

## Contributions
We welcome pull requests if you feel like something could be improved. You can also greatly help us by telling us how you felt when writing your most recent tweets. Just click [here](http://deepmoji.mit.edu/contribute/) to contribute.

## License
This code and the pretrained model is licensed under the MIT license.

## Benchmark datasets
The benchmark datasets are uploaded to this repository for convenience purposes only. They were not released by us and we do not claim any rights on them. Use the datasets at your responsibility and make sure you fulfill the licenses that they were released with. If you use any of the benchmark datasets please consider citing the original authors.

## Citation
```
@inproceedings{felbo2017,
  title={Using millions of emoji occurrences to learn any-domain representations for detecting sentiment, emotion and sarcasm},
  author={Felbo, Bjarke and Mislove, Alan and S{\o}gaard, Anders and Rahwan, Iyad and Lehmann, Sune},
  booktitle={Conference on Empirical Methods in Natural Language Processing (EMNLP)},
  year={2017}
}
```
