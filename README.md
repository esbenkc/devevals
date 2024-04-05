# Developmental Evaluations

Inspired by [devinterp](https://github.com/timaeus-research/devinterp), we instead develop a developmental landscape based on performance on dangerous capabilities benchmarks.

This differs from layer-based nonlinear probes by investigating the development of capability throughout training.

This differs from developmental interpretability by constructing the training space from evaluation benchmark results.

The most comprehensive research in this direction is related to the Pythia model suite evaluations, running e.g. [SciQ](https://allenai.org/data/sciq) accuracy over the number of tokens trained for all 8 models (70M through 12B).

Despite the wish for Pythia models to be an opportunity to do in-depth developmental interpretability over the standardize learning schemas, surprisingly few papers have come out that investigate this. Mostly, researchers have evaluated models of varied sizes and origins, developing so-called ["Scaling Laws"](https://arxiv.org/abs/2001.08361).

## Experimental design

We take a series of benchmarks used for evaluating dangerous capabilities and test them on the [Pythia model series](https://huggingface.co/EleutherAI/pythia-12b-deduped) saved at multiple checkpoints for the 12B model.

Datasets evaluated:

- [Hate Speceh and Offensive Language Dataset](https://www.kaggle.com/datasets/mrmorj/hate-speech-and-offensive-language-dataset)
- [HateXplain](https://hatespeechdata.com/) including annotations for level of hate speech included
- Other datasets accurately covering the dangerous capabilities and capabilities space (MMLU etc.)

From these datasets, we get performance metrics over training steps that together represent a type of feature space we can conduct PCA over.

We can investigate the principal components to understand what sort of patterns show up and investigate their training trajectory.

Additionally, we can attempt to compare sudden emergence of dangerous capabilities (["grokking"](https://arxiv.org/abs/2201.02177)) from the datasets to sudden potential shifts in the training trajectory.
