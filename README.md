# Mental Health in Literature Analysis disorders

## Overview

In this project, we tried to diagnose literary characters with mental disorders according to [International Classification of Diseases (ICD)](https://icd.who.int/en).

Try out our [mini-app](https://huggingface.co/spaces/NursNurs/detect_mental_disorder) where you can diagnose any other literary character, or even yourself, based on provided description (please, note this can't be used for diagnostics and can be used for entertainment only).

## Project Structure 

    ├── LICENSE
    ├── README.md
    ├── code
    │   ├── 1 - ICD_API.ipynb
    │   ├── 2 - ICD_Embeddings.ipynb
    │   ├── 3 - Characters_Embeddings.ipynb
    │   ├── 4 - Cos_sim + projections.ipynb
    │   └── 5 - Visualization.ipynb
    ├── data
    │   ├── characters_data
    │   ├── characters_disorders
    │   ├── characters_embeddings
    │   ├── characters_plots
    │   └── icd_data
    └── report

## Background & Motivation

Madness is a very prominent yet controversial topic; every society in different periods of time approached it differently. Some cultures ostracize and isolate "crazy" people, some cultures hold them for saint. It hasn't been so long since psychiatry developed as a science, and the classfication and diagnostic criteria for various disorders were developed (let alone the fact that what is considered as a disorder has also undergone changes).

<strong>Many writers have described madness in their work without having any labels for the disorders.<strong>

Some traits weren't recognized as symptoms even; for instance, sleeping all the time and having no energy could be acribed to lazyness and faulty character rather than, say, depression, and what is now considered as a bipolar disorder could be viewed as a moody personality. Since strict labels and diagnostic criteria didn't exist, we can only assume which disorders the authors described. And since writers often capture the spirit of their time in their work - whether by choice or by design - we can estimate societal views and attitudes to madness from their writings.

There are many questions one can pose:

    <strong>Do depicted disorders differ by time period/country/author?<strong>
    <strong>Do popularly described disorders correlate with historical events/context?<strong> For example, can it be that after wars, more literary characters were described with PTSD, and after famine more characters had eating disorders?
    <strong>Do male and female characters differ in what disorders are assigned to them?<strong> For example, could female characters be more often associated with depression and histeria, while male characters - with schizophrenia and asocial disorders?

This work is an attempt to address some of these questions using computational approach.


## Methodology

There are many questions one can pose:

1. Get descriptions of characters. For this step, we used ChatGPT using the same prompt for each character. If ChatGPT was confused or tried to claim such a character doesn't exist, we discarded the character to not include false data on purpose. While this step is not perfect, it allowed us to get preliminary descriptions of each character that were of the same size, style, and format.
2. Get descriptions of disorders. For this step, we used [API](https://icd.who.int/en) of the ICD.
3. Preprocess descriptions (tokenize, remove stop-words, lemmatize, etc.)
4. Convert all descriptions into embeddings. We used sentence transformers.
6. Compute the cosine similarity between each character and each disorder description.
7. Process and visualize the results (group by gender, time, country).

## Visualizations & Analysis

We utilized the Plotly library for creating the visualizations of computed embeddings for the characters of each author under analysis, which can be found [here](https://nursaltyn.github.io/projects/project_literature/project_literature.html). Additionally, we performed comparative analysis of the obtained data, presented on the same [page](https://nursaltyn.github.io/projects/project_literature/project_literature.html).


## Future plans

- Get high-quality descriptions of characters (e.g., through crowdsourcing)
- Obtain more detailed descriptions of disorders
- Cover more authors and countries for representativeness
- Identify a threshold for accepting a diagnose (not all characters have to have disorders!)

### Dependencies
- Python 3.x
- Required Python packages (install using pip install -r requirements.txt)

## Acknowledgments
- [International Classification of Diseases](https://icd.who.int/en)