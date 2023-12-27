# Analysis of business documents
Identification of business document topics and extraction of the business industry entity based on ML/AI models

## Data
https://www.kaggle.com/datasets/jensenbaxter/10dataset-text-document-classification?select=business

## How to reproduce
1. download the data and place them at data directory
2. create conda env from requirements.yaml
```
conda env create -f environment.yml 
```

## Repo
The repository consists of the following files:
* environment.yml - reproduction file
* entity-extractor.ipynb, which contains a solution that uses the gpt3 API (3.5 turbo) to extract a business entity from the given text. The model selects a business entity from a previously defined list, which allows you to adapt the list of industries to a specific task, as well as sorting and filtering next items per business. 
An analogous version of the application enabling inference is available: https://huggingface.co/spaces/swiatowiec/business-entity-extractor
* extracted-entities.json - obtained using extity-extractor.ipynb entities and the texts they concern
* title-generator.ipynb - a file that generates title based on text. In this script, gpt2 was used as a baseline (model + tokenizer) and then it was fine-tuned using provided data. The solution is based on the assumption that each business note contains a title in the first line, and the remaining lines are the content.
