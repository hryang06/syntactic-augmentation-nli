# syntactic-augmentation-nli

This repository contains the syntactic augmentation dataset to improve robustness in NLI, used in our ACL 2020 paper, Syntactic Data Augmentation Increases Robustness to Inference Heuristics, by Junghyun Min<sup>1</sup>, Tom McCoy<sup>1</sup>, Dipanjan Das<sup>2</sup>, Emily Pitler<sup>2</sup>, and Tal Linzen<sup>1</sup>.

<sup>1</sup>Department of Cognitive Science, Johns Hopkins University, Baltimore, MD

<sup>2</sup>Google AI Language, New York, NY

## Data

Augmentation datasets are in the [`datasets`](https://github.com/Aatlantise/qa2/tree/master/datasets) folder. Each file is named using the following abbreviations:

Transformation strategies:
- `inv`: inversion
- `pass`: passivization
- `comb`: combination of inversion and passivization
- `chaos`: random shuffling condition

Sentence pair:
- `orig`: original premise as premise, tranformed hypothesis as hypothesis
- `trsf`: original hypothesis as premise, transformed hypothesis as hypothesis

Label:
- `pos`: augmentation examples whose label is entailment
- `neg`: augmentation examples whose label is nonentailment

Size:
- `small`: 101 examples
- `medium`: 405 examples
- `large`: 1215 examples

For example, [`pass_orig_pos_small.tsv`](https://github.com/Aatlantise/qa2/tree/master/datasets/pass_orig_pos_small.tsv) is an set of 101 original premise-passivized hypothesis pair whose labels are entailment. Fields within each file are equivalent to those from the [MultiNLI](https://github.com/nyu-mll/multiNLI) dataset. However, only four fields `index`, `sentence1` (premise), `sentence2` (hypothesis), and `gold_label` are populated.

## Script

The attached `.tsv` data files were used to augment the MultiNLI training set in our experiments. They are randomly selected subsets or unions of subsets of transformations created by running [`qa2.py`](https://github.com/Aatlantise/qa2/tree/master/qa2.py) on Python 2. It requires MultiNLI's json file to run.

## Config

BERT parameters and other configurations used to train augmented models are included in the [`config`](https://github.com/Aatlantise/qa2/tree/master/config) folder.

