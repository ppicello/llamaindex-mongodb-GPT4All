# llamaindex-mongodb-GPT4All

![header](/docs/header.png?raw=true "header")

> **Note**
> I am still very new to LlamaIndex and generative AI in general and the reason why I started this repo was to start learning a bit more on that and start exploring the capabilities we will have in this domain. Obviously this is not intended to be production-ready or not even poc-ready I'd say. This is just a fun experiment!

This repo contains a Python notebook to show how you can integrate MongoDB with [LlamaIndex](https://gpt-index.readthedocs.io/en/latest/) to use your own private data with tools like ChatGPT. Your data are fed into the LLM using a technique called "in-context learning".  To do so we leverage the Mongo Loader available in [LlamaHub](https://llamahub.ai/l/mongo). 
A big part of this exercise was to demonstrate how you can use a locally running model like [GPT4All](https://gpt4all.io/index.html) instead of OpenAI ChatGPT, and [HuggingFace](https://huggingface.co/) transformers .
All the code can be executed completely on CPU.

The step are explained in the notebook but basically we leveraged the `sample_mflix-movies` collection part of the sample dataset available in [MongoDB Atlas](https://www.mongodb.com/atlas/database). We index the documents in the collection and on top of them I created a fictitious document for a fictitious movie called "The Paolo Picello movie", describing the life of a Solutions Architect trying to build cool apps with AI and MongoDB.

![movie](/docs/paolopicellomovie.png?raw=true "movie")


I then provided the following question to the system:

`What is the name of the movie that talks about a computer engineer trying to build a demo of how you can leverage AI tools to answer questions around data stored in MongoDB?"`

and the system answer:

`The name of the movie is "PaoLo Picello".`

Interestingly, the system was able to get my name out of its corpus. This is not the exact name we specified in the MongoDB document ("The Paolo Picello movie") but it's still a quite impressive result. 

![movie](/docs/response.png?raw=true "movie")


> **Note**
> The system allucinate quite a lot, giving most of the times pretty random results. But it's still fascinating to see the system able to get my name out as response. 

## Possibile next steps

- Levearage a vector database to store the indexes
- Find a much more relevant example/use case
- Integrate with [HuggingChat](https://huggingface.co/chat/)
- Run on GPU (before that I need to buy a GPU lol)
- Improve the Mongo Loader available in LlamaHub. You have too little control over the document creation. 

## Credits

This notebook is inspired by the [LlamaIndex - Local Model Demo.ipynb](LlamaIndex - Local Model Demo.ipynb) notebook referred in the [LlamaIndex documentation](https://gpt-index.readthedocs.io/en/latest/guides/tutorials.html).


We welcome comments and contribution!!










