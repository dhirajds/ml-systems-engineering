# We will try to build an dataset that can be used to train and test our LLM.
# Since we use a decoder only architecture like GPT.
# we will concentrate on next token prediction.

# how big can be this input to predict the next token.
# that is decided by context size..
# If input is smaller...then its fine...cant be larger than context size.


# Create dataset from the input data:
# only reference required for creating this class.
# https://docs.pytorch.org/tutorials/beginner/basics/data_tutorial.html

"PyTorch provides two data primitives: torch.utils.data.DataLoader and torch.utils.data.Dataset that allow you to use pre-loaded datasets as well as your own data. Dataset stores the samples and their corresponding labels, and DataLoader wraps an iterable around the Dataset to enable easy access to the samples."

"Creating a Custom Dataset for your files
A custom Dataset class must implement three functions: __init__, __len__, and __getitem__. "


Preparing your data for training with DataLoaders
The Dataset retrieves our dataset’s features and labels one sample at a time. While training a model, we typically want to pass samples in “minibatches”, reshuffle the data at every epoch to reduce model overfitting, and use Python’s multiprocessing to speed up data retrieval.


from torch.utils.data import DataLoader

train_dataloader = DataLoader(training_data, batch_size=64, shuffle=True)
test_dataloader = DataLoader(test_data, batch_size=64, shuffle=True)


# what X, and Y will be returned is another thing.
