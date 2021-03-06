---
layout: post
title: Chatbot
description: Chatbot trained in English and Mandarin with Transformer Model from Google Brain
image: assets/images/chatbot.jpeg
nav-menu: true
---

## Introduction
The main goal of this project is to implement a chit-chat bot using Transformer, which is a state-of-art model with Attention based on the paper from Google Brain, ["Attention is All You Need"](https://arxiv.org/abs/1706.03762).

Through the command line interface, a can run the eval.py script and then interact with the chatbot by typing in prompts directly on the command line. Based on the data on which the model is trained, an appropriate response will be constructed and printed at the command line.

## Requirements
* Tensorflow 
* NLTK
* Regex
* Numpy
* JSON
* GPU(not necessary, for optimized running)

## Data
One major part of this project is to collect and preprocess as much data as we could to feed into the model and improve the performance. There are several dataset source being used for this project: [Cornell Movie Dialogs Corpus](http://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html), Twitter Chat Corpus, Ubuntu Chat Dialogues and [Reddit Comment Threads](https://www.reddit.com/r/datasets/comments/3bxlg7/i_have_every_publicly_available_reddit_comment/).

All these raw data are in different formats, size, and storage methods. In order to apply all of these data to one model, we have to **pre-process** them.

## Pre-processing
NLTK and Regex have been the two mainly used tools for data pre-processing.

For separated-column-type text data (i.e. movie corpus), `nltk.tokenize` library or `split()` function from Regex could both easily split the raw text by space and retrieve the content of conversation. For nested JSON files (i.e. Reddit threads), `json.load()` and `string.filter()` functions could help finding useful json tags.

After removing non-related headers, tags and separators, we found that the text data still contains lots of non-Unicode characters which could raise error when training. In this case, we simply check each line and keep only alphabetical characters and basic symbols.

## File Structure

### ./transformer
This is the root directory of the project, containing Transformer modules, training script and evaluation script.

### ./transformer/chatbotData
This directory has all the raw data extracted from multiple sources, the preprocessing scripts and cleaned data.

### ./transformer/models
This directory is where the trained model being stored.

### ./media
This directory contains a demonstration. Check out the quick demo video [here](https://github.com/ThePenultimatum/shriekinDesparado/blob/dev/media/demo.mp4)

### ./processing
This is the directory containing all of the processing and data scraping scripts we used in order to construct the input prompts.txt and responses.txt files for training the model.

### ./scripts
This is a directory containing any shell runscripts. Currently, there is only trainAndPredict.sh which runs the preprocessing, training, and evaluation all in one script. This can be executed with the following command:
```bash
./trainAndPredict
```

## Getting Started

### Installing

Clone or fork this repo.

```bash
git clone https://github.com/ThePenultimatum/shriekinDesparado.git
```

Enter the directory. Ensure the data you want to train on is in the chatbotData directory. Or you can use the default hyperparameters just to test immediately.

Data will be in the format of two files for training.
prompts.txt and responses.txt
Each newline separated prompt and response in these files must be in order such that line 0 in each file corresponds to a prompt and response pair. If this is not the case, then the data will not be trained on properly.

* Run the preprocessing prepro.py
```bash
python prepro.py
```

* Run train.py
```bash
python train.py
```

* Then run eval.py
```bash
python eval.py
```

This will bring up a command line prompt for you to type something into the command line and hit enter. This will submit your text to the trained model for prediction and will return a response predicted based on the training data.

## Deployment
Using a pretrained model can expedite your chatbot experience. Here is a zip file with pretrained hyperparameters.
[Twitter Pretrained Model](https://drive.google.com/open?id=1Tk3K46neJPiC2KITnt_fhLSLhBL0F8p3)

This would be placed in the directory with eval.py when you run that.

## Contributing

If modifying or contributing to the transformer code, refer to Kyubyong Park's transformer repository contribution standards.

If contributing to the modifications in our project here, please follow the following steps:
* Fork the repository
* Add your modifications to either the dev branch or a branch off of the dev branch
* Make a pull request with informative descriptions

## Versioning

There is only one version as of now, and that is the version committed in the master branch.
Master branch commits define the versions, but we will be utilizing tags for versions soon.

## Team

* **Yuchen Wang** - *Initial work* - [yuchnw](https://github.com/yuchnw)
* **Mark Dyehouse** - *Initial work* - [ThePenultimatum](https://github.com/ThePenultimatum)

See also the list of [contributors](https://github.com/ThePenultimatum/shriekingDesparado/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Acknowledgments

* Google Brain team from the paper "Attention is All You Need" who originally detailed the Transformer model
* GitHub user [Kyubyong Park](https://github.com/Kyubyong) for his work on developing a usable [Transformer](https://github.com/Kyubyong/transformer) in Python
* Dr. Han Liu of Northwestern University