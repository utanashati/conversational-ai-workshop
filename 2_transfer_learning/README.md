# Task 2: Transfer learning
In task 1, we learned about chatbots and trained our first language model.

In this task, we will start with a language model that was pretrained on a large corpus of data from all kinds of sources to narrow it down to a domain and task of choice (a specific style for conversation generation).

## Important resources
* [Workshop Github repo](https://github.com/utanashati/conversational-ai-workshop)
* [PyTorch documentation](https://pytorch.org/docs/stable/index.html)
* Huggingface transformers library [ [Github](https://github.com/huggingface/transformers) | [Docs](https://huggingface.co/transformers/) ]

# Approach
To "teach" the model the structure of a conversation, we will utilize a naive approach of simply feeding the model "raw" conversations data of the form:
```
<speaker1> Hi
<speaker2> Hey - how are you?
<speaker1> Great, thanks!
...
```
Our hope is that the model will learn this structure and we will  be able to query our model with an input of the form:

```
<speaker2> Am I speaking to a bot?
<speaker1>
```
We then expect the model to extend the text from this prefix.

In the provided notebook, you will go through all the steps fo this process, from collecting the training data to interacting with the final model.

# Data
You are free to either use either your own chat logs or conversational data from other sources. 

## Dataset 1: World leader interviews

The first option is a dataset of interviews of two world leaders, Barack Obama and Vladimir Putin. These interviews will be treated as chat conversations, where the reporters are the interlocutors.

## Dataset 2: Movie quotes

Another option is to use quotes from movies. You can use the [Cornell Movie-Dialogs Corpus](https://), which contains **220,579 conversational exchanges** between 10,292 pairs of movie characters.

# Usage
You can either run this code locally or use the Colab notebook.

## Local
1. Clone this repository using
```
git clone https://github.com/utanashati/conversational-ai-workshop.git && cd conversational-ai-workshop
```
2. Install the dependencies
Make sure you have PyTorch with GPU-support installed. Follow the instructions [here](https://pytorch.org/get-started/locally/) here to install the proper version depending on your OS. Then run:
```
cd 2
pip install -r requirements.txt
```
3. Make sure you have a single JSON file in the folder `2_transfer_learning/datasets/` (otherwise specify the `--data_path` argument) and run
```
python train.py --run_name run1
```
4. Interact with the model by running
```
python interact.py --run_name run1
```

## Colab notebook
[![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1P0AqDEOZwtBt-mzNSjeCeIim7J53zAxd)
