language: bn
tags:
- collaborative
- bengali
- Sequence classification
license: apache-2.0
datasets: IndicGlue 
metrics:
- Loss
- Accuracy
- Precision
- Recall
---

# sahajBERT Named Entity Recognition

## Model description

[sahajBERT](https://huggingface.co/neuropark/sahajBERT-NER) fine-tuned for news article classification using the `sna.bn` split of [IndicGlue](https://huggingface.co/datasets/indic_glue). 

The model is trained for classifying articles into 5 different classes:

| Label id | Label |
|:--------:|:----:|
|0 | kolkata|
|1 | state|
|2 | national|
|3 | sports|
|4 | entertainment|
|5 | international|

## Intended uses & limitations

#### How to use

You can use this model directly with a pipeline for Sequence Classification:
```python
from transformers import AlbertForSequenceClassification, TextClassificationPipeline, PreTrainedTokenizerFast

# Initialize tokenizer
tokenizer = PreTrainedTokenizerFast.from_pretrained("neuropark/sahajBERT-NCC")

# Initialize model
model = AlbertForSequenceClassification.from_pretrained("neuropark/sahajBERT-NCC")

# Initialize pipeline
pipeline = TextClassificationPipeline(tokenizer=tokenizer, model=model)

raw_text = "এই ইউনিয়নে ৩ টি মৌজা ও ১০ টি গ্রাম আছে ।" # Change me
output = pipeline(raw_text)
```

#### Limitations and bias

<!-- Provide examples of latent issues and potential remediations. -->
WIP

## Training data

The model was initialized with pre-trained weights of [sahajBERT](https://huggingface.co/neuropark/sahajBERT-NER) at step TODO_REPLACE_BY_STEP_NAME and trained on the `sna.bn` split of [IndicGlue](https://huggingface.co/datasets/indic_glue). 

## Training procedure

Coming soon! 
<!-- ```bibtex
@inproceedings{...,
  year={2020}
}
``` -->

## Eval results

Loss: 0.2477145493030548

Accuracy: 0.926293408929837

Macro F1: 0.9079785326650756

Recall: 0.926293408929837

Weighted F1: 0.9266428029354202

Macro Precision: 0.9109938492260489

Micro Precision: 0.926293408929837

Weighted Precision: 0.9288535478995414

Macro Recall: 0.9069095007692186

Micro Recall: 0.926293408929837

Weighted Recall: 0.926293408929837

### BibTeX entry and citation info

Coming soon! 
<!-- ```bibtex
@inproceedings{...,
  year={2020}
}
``` -->