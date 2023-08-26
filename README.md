# Arabic Broken Plurals


## Quick literature review:
### McCarthy & Prince 1990 (Foot and word in prosodic morphology: The Arabic broken plural)
They argue that the prosodic pattern is what determines the plural pattern. The conclusion is that the iambic broken plural pattern is the most productive and is the default plural pattern.

Mc&Pr take on plurals:
>Both languages [Arabic and English] organize their morphologies into a special case/general case structure, suffixing by default when the other competing inflectional modes are inapplicable, and both languages require that the input to the specialized system meet standards of canonicality, phonological (stem-shape patterns) and morphological (nonderived status).

> In Arabic the "special case" system is fully articulated and relatively few items escape it to end up with the default "sound" suffix. For the lexicon as a whole, then, broken plural formation is by far the norm rather than the exception.

Sound Plural:
>Although the term "sound plural" suggests normality - and indeed its form is entirely predictable from gender and other grammatical information - the sound plural is in no way the regular or usual mode of pluralization.

>The sound plural is systematically found only with members of the following short list: **proper names**; **transparently derived nouns or adjectives such as participles, deverbals, and diminutives** ( Levy 1971); **noncanonical or unassimilated loans (tilifuun/tilifuun+aat);** and **the names of the letters of the alphabet**, which are mostly noncanonical

Broken Plural:
>Essentially all canonically-shaped lexical nouns of Arabic take broken plurals, including many loans, even very recent ones: _film/aflaam 'film'_; _bank/bunuuk 'bank'_.

> ... we need to keep one eye on the prosodic structure of the plural patterns and the other on their actual lexical distribution ...

The focus is obviously on broken plurals.


## Description
Two different datasets are used in this project

### Data Preprocess

- #### Duplicate Plurals
  > a single lemma might have different plural forms (broken or sound). So, only one of the plural forms which has the most frequency is used.
  
- #### Encoding Data
  > Character based encoding is used in this project, because we hd to predict the exact plural word for each lemma

## Approaches
### Classification Model
only on first dataset
> model used for classifying the type of plural form for each lemma (broken or sound)

> output of this model is used as an input feature for machine translation task for each lemma to improve the results

### Embedding Model (BERT)
> The BERT Embedding output is used as an input feature for the machine translation task for each lemma to improve the results

### Machine Translation Model
> this model uses different input features to predict the plural form of each lemma

> beacuse the words are encoded using character based approch, we have two accuracy measurements, one for each character in the word and other for thw whole word itself

## Results
we can see that most of our errors on both datasets are among unseen data and also broken plural forms
