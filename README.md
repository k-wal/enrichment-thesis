# Enriching Partial Annotations for Named Entity Recognition

## Abstract

This research proposes Enrichment, a novel approach to utilize previously labelled datasets to enhance partially annotated datasets. Experimental results show that enrichment significantly outperforms models trained on non-enriched datasets, resulting in an improvement of atleast 21% in F1-score on datasets from three different domains.

## Experiments

### Datasets
Experiments were conducted on datasets from three domains (Biomedical, Material Science, Computer Science). To create partially annotated sets, 60\% of all entities were removed from fully annotated sets.

### Baselines
The baselines for this research are:
* BERT-partial: fine-tuning the domain-specific BERT model on partially annotated datasets. Since BERT models represent state-of-the-art methods, this baseline is useful in directly measuring the impact of Enrichment against state-of-the-art methods on partial datasets
* BERT-add: fine-tuning the domain-specific BERT model on manually annotated datasets. This baseline helps quantify the usefulness of considering the partially annotated set at all. 
* BOND: BERT Assisted Open-Domain NER, the state-of-the-art method to deal with distantly-supervised datasets


### Results

#### Biomedical Domain
|     Model    | Precision | Recall | F1-score |
|:------------:|:---------:|:------:|:--------:|
| BERT-partial | 0.91      | 0.38   | 0.53     |
|   BERT-add   | 0.54      | 0.78   | 0.63     |
|     BOND     | 0.54      | 0.51   | 0.57     |
|  Enrichment  | 0.73      | 0.74   | 0.74     |

#### Material Science Domain
|     Model    | Precision | Recall | F1-score |
|:------------:|:---------:|:------:|:--------:|
| BERT-partial | 0.86      | 0.34   | 0.48     |
|   BERT-add   | 0.50      | 0.53   | 0.51     |
|     BOND     | 0.87      | 0.76   | 0.81     |
|  Enrichment  | 0.65      | 0.80   | 0.72     |

#### Computer Science Domain
|     Model    | Precision | Recall | F1-score |
|:------------:|:---------:|:------:|:--------:|
| BERT-partial | 0.68      | 0.28   | 0.40     |
|   BERT-add   | 0.71      | 0.44   | 0.55     |
|     BOND     | 0.95      | 0.50   | 0.65     |
|  Enrichment  | 0.74      | 0.67   | 0.71     |


## File Structure
├── data-prep
├── code
├── corpus

* `data-prep` contains all data preprocessing notebooks and exploratory data analysis
* `code` contains the notebooks with enrichment and baselines
* `corpus` contains datasets in their original form, and in their processed form
