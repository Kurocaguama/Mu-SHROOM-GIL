# Mu-SHROOM @ SemEval 2025: Unlabeled train set
This archive corresponds to the Unlabeled train data for the Mu-SHROOM shared task 3 at Semeval 2025 (The Multilingual Shared-task on Hallucinations and Observable Overgeneration Mistakes).
It contains:
1. the present README,
2. JSONL files containing the annotated data corresponding to our validation split (henceforth "the data files").

There are separate files for a subset of the languages of the shared task : Chinese, English, French, and Spanish.

## What is Mu-SHROOM?
The task consists in detecting spans of text corresponding to hallucinations. 
Participants are asked to determine which parts of a given text produced by LLMs constitute hallucinations.
The task is held in multi-lingual and multi-model context, i.e., we provide data in multiple languages and produced by a variety of public-weights LLMs.

This task is a follow-up on last year's SemEval Task 6 (SHROOM).

More information is available on the official task website: 
https://helsinki-nlp.github.io/shroom/

## Data file format
The data files are formatted as a JSON lines. Each line is a JSON dict object and corresponds to an individual datapoint.

Each datapoint corresponds to a different annotated LLM production, and contains the following information:
- a unique datapoint identifier (`id')
- a language (`lang');
- a model input question (`model_input`), the input passed to the models for generation;
- a model identifier (`model_id`) denoting the HuggingFace identifier of the corresponding model;
- a model output (`model_output_text`), the output generated by a LLM when provided the aforementiond input;
- a list of model output tokens (`model_output_tokens`), corresponding to the tokenized output of the LLM response,
- a list of logit values for the tokens generated in the LLM response (`model_output_logits`).


## How will this dataset differ from upcoming data releases?
The train set is unlabeled and does not cover all languages.

- We are considering adding extra languages to this train set;
- A v2 of the validation split is on the way, which will provide extra information on datapoint generation;
- We intend to release supplementary details after the evaluation phase.

