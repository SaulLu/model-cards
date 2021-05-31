---

language: bn

tags:

- collaborative

- bengali

- albert

- bangla

license: apache-2.0

datasets:

- Wikipedia

- Oscar

widget:

- text: "ধন্যবাদ। আপনার সাথে কথা [MASK] ভালো লাগলো"

---

<!-- TODO: change widget text -->

# sahajBERT

Collaboratively pre-trained model on Bengali language using masked language modeling (MLM) and Sentence Order Prediction (SOP) objectives. 

## Model description

<!-- You can embed local or remote images using `![](...)` -->

sahajBERT is a model composed of 1) a tokenizer specially designed for Bengali and an [ALBERT](https://arxiv.org/abs/1909.11942) architecture collaboratively pre-trained on a dump of Wikipedia in Bengali and the Bengali part of OSCAR. 

<!-- Add more information about the collaborative training when we have time / preprint available -->

## Intended uses & limitations

You can use the raw model for either masked language modeling or next sentence prediction, but it's mostly intended to be fine-tuned on a downstream task that use the whole sentence (potentially masked) to make decisions, such as sequence classification, token classification or question answering.

We trained our model on 2 of these downstream tasks: [sequence classification](https://huggingface.co/neuropark/sahajBERT-NCC) and [token classification](https://huggingface.co/neuropark/sahajBERT-NER)

#### How to use

You can use this model directly with a pipeline for masked language modeling:

```python

from transformers import AlbertForMaskedLM, FillMaskPipeline, PreTrainedTokenizerFast

# Initialize tokenizer

tokenizer = PreTrainedTokenizerFast.from_pretrained("neuropark/sahajBERT")

# Initialize model

model = AlbertForMaskedLM.from_pretrained("neuropark/sahajBERT")

# Initialize pipeline

pipeline = FillMaskPipeline(tokenizer=tokenizer, model=model)

raw_text = "ধন্যবাদ। আপনার সাথে কথা [MASK] ভালো লাগলো" # Change me

pipeline(raw_text)

```

Here is how to use this model to get the features of a given text in PyTorch:

```python

from transformers import AlbertModel, PreTrainedTokenizerFast

# Initialize tokenizer

tokenizer = PreTrainedTokenizerFast.from_pretrained("neuropark/sahajBERT")

# Initialize model

model = AlbertModel.from_pretrained("neuropark/sahajBERT")

text = "ধন্যবাদ। আপনার সাথে কথা বলে ভালো লাগলো" # Change me

encoded_input = tokenizer(text, return_tensors='pt')

output = model(**encoded_input

```

#### Limitations and bias

<!-- Provide examples of latent issues and potential remediations. -->

WIP

## Training data

The tokenizer was trained on he Bengali part of OSCAR and the model on a [dump of Wikipedia in Bengali](https://huggingface.co/datasets/lhoestq/wikipedia_bn) and the Bengali part of [OSCAR](https://huggingface.co/datasets/oscar).

## Training procedure

This model was trained in a collaborative manner by volunteer participants. 

<!-- Add more information about the collaborative training when we have time / preprint available + Preprocessing, hardware used, hyperparameters... (maybe use figures)-->

### Contributors leaderboard

| Rank       | Username           | Total contributed runtime  |

|:-------------:|:-------------:|-------------:|

| 1|[khalidsaifullaah](https://huggingface.co/khalidsaifullaah)|11 days 21:02:08|

| 2|[ishanbagchi](https://huggingface.co/ishanbagchi)|9 days 20:37:00|

| 3|[tanmoyio](https://huggingface.co/tanmoyio)|9 days 18:08:34|

| 4|[debajit](https://huggingface.co/debajit)|8 days 14:15:10|

| 5|[skylord](https://huggingface.co/skylord)|6 days 16:35:29|

| 6|[ibraheemmoosa](https://huggingface.co/ibraheemmoosa)|5 days 01:05:57|

| 7|[SaulLu](https://huggingface.co/SaulLu)|5 days 00:46:36|

| 8|[lhoestq](https://huggingface.co/lhoestq)|4 days 20:11:16|

| 9|[nilavya](https://huggingface.co/nilavya)|4 days 08:51:51|

|10|[Priyadarshan](https://huggingface.co/Priyadarshan)|4 days 02:28:55|

|11|[anuragshas](https://huggingface.co/anuragshas)|3 days 05:00:55|

|12|[sujitpal](https://huggingface.co/sujitpal)|2 days 20:52:33|

|13|[manandey](https://huggingface.co/manandey)|2 days 16:17:13|

|14|[albertvillanova](https://huggingface.co/albertvillanova)|2 days 14:14:31|

|15|[justheuristic](https://huggingface.co/justheuristic)|2 days 13:20:52|

|16|[w0lfw1tz](https://huggingface.co/w0lfw1tz)|2 days 07:22:48|

|17|[smoker](https://huggingface.co/smoker)|2 days 02:52:03|

|18|[Soumi](https://huggingface.co/Soumi)|1 days 20:42:02|

|19|[Anjali](https://huggingface.co/Anjali)|1 days 16:28:00|

|20|[OptimusPrime](https://huggingface.co/OptimusPrime)|1 days 09:16:57|

|21|[theainerd](https://huggingface.co/theainerd)|1 days 04:48:57|

|22|[yhn112](https://huggingface.co/yhn112)|0 days 20:57:02|

|23|[kolk](https://huggingface.co/kolk)|0 days 17:57:37|

|24|[arnab](https://huggingface.co/arnab)|0 days 17:54:12|

|25|[imavijit](https://huggingface.co/imavijit)|0 days 16:07:26|

|26|[osanseviero](https://huggingface.co/osanseviero)|0 days 14:16:45|

|27|[subhranilsarkar](https://huggingface.co/subhranilsarkar)|0 days 13:04:46|

|28|[sagnik1511](https://huggingface.co/sagnik1511)|0 days 12:24:57|

|29|[anindabitm](https://huggingface.co/anindabitm)|0 days 08:56:44|

|30|[borzunov](https://huggingface.co/borzunov)|0 days 04:07:35|

|31|[thomwolf](https://huggingface.co/thomwolf)|0 days 03:53:15|

|32|[priyadarshan](https://huggingface.co/priyadarshan)|0 days 03:40:11|

|33|[ali007](https://huggingface.co/ali007)|0 days 03:34:37|

|34|[sbrandeis](https://huggingface.co/sbrandeis)|0 days 03:18:16|

|35|[Preetha](https://huggingface.co/Preetha)|0 days 03:13:47|

|36|[Mrinal](https://huggingface.co/Mrinal)|0 days 03:01:43|

|37|[laxya007](https://huggingface.co/laxya007)|0 days 02:18:34|

|38|[lewtun](https://huggingface.co/lewtun)|0 days 00:34:43|

|39|[Rounak](https://huggingface.co/Rounak)|0 days 00:26:10|

|40|[kshmax](https://huggingface.co/kshmax)|0 days 00:06:38|

## Eval results

We evaluate sahajBERT model quality and 2 other model benchmarks ([XLM-R-large](https://huggingface.co/xlm-roberta-large)  and [IndicBert](https://huggingface.co/ai4bharat/indic-bert)) by fine-tuning 3 times their pre-trained models on two downstream tasks in Bengali:

- **NER**: a named entity recognition on Bengali split of [WikiANN](https://huggingface.co/datasets/wikiann) dataset

- **NCC**: a multi-class classification task on news Soham News Category Classification dataset from IndicGLUE

| Base pretrained Model       | NER - F1 (mean ± std) | NCC - Accuracy (mean ± std)           |

|:-------------:|:-------------:|:-------------:|

|sahajBERT |  95.45 ± 0.53|  91.97 ± 0.47|

|[XLM-R-large](https://huggingface.co/xlm-roberta-large) |  96.48 ± 0.22| 90.05 ± 0.38|

|[IndicBert](https://huggingface.co/ai4bharat/indic-bert) |  92.52 ± 0.45| 74.46 ± 1.91|

### BibTeX entry and citation info

Coming soon! 

<!-- ```bibtex

@inproceedings{...,

  year={2020}

}

``` -->