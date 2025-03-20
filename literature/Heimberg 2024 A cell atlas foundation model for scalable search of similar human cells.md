# A cell atlas foundation model for scalable search of similar human cells

| Author(s)         | Year of Publication |
|-------------------|---------------------|
| Heimberg et al.   | 2024                |

## Highlights

- Developed SCimilarity, a deep-metric-learning foundation model that
quantified similarity between single-cell profiles
- Trained SCimilarity with 23.4 million macrophage and fibroblast cells in interstitial lung disease.
- SCimilarity’s loss function decouples faithful cell representation 
(query) from sample mixing (integration) and learns features that 
capture meaningful biology, reduce technical noise and generalizes to 
data held out of the training set.


## Training datasets

- Focused on scRNA and snRNA from 10x genomics chromium platform.
- The datasets were sourced from GEO and CELLxGENE.
- Data were preprocessed with similar pipeline.
- 412 studies, ~23 million cell profiles, 5142 tissue samples (184 unique Tissue
Ontology terms), 132 Disease Ontology terms.
- Training set: ~8 million cell profiles from 56 studies with 203 Cell Ontology 
 terms. 
 - Validation: 15 studies with ~1.4 million cells

## Results

- Optimizing reconstruction loss led to better query performance
- Optimizing triplet loss led to better integration benchmarks
- Query performance was better than scFoundation and scGPT
- Integration performance was better than existing tools such as
  Harmony, scVI, scanorama, and scArches.
- The trained model also generalizes well to test data from 
  other platforms.
- 79.5 % of in vivo holdout cell had high representation confidence.
- 43.8% for in vitro
- Assembled an atlas of 30 human tissues and shared the embeddings 
  as part of the SCimilarity distribution
- Cell type annotation is done by matching the most similar cells in the 
  reference.
- The annotation level by SCimilarity was competitive with other 
  methods trained specifically for a certain tissue type.
- The model showed that fibrosis-associated macrophage is common in ILD lung
  samples.




## Generalization across platforms


## Concepts

### Cell triplet
Cell triplet consists of anchor, positive and negative cells. The anchor and 
positive cells are of same cell type from from different datasets, while the
anchor and negative cells are of different cell type from the same or different
datasets.

## Challenges
Some existing cell type annotations are ambiguous in terms of granularity. 
For example, one study may label cells with T cell, while another study
may label same cells CD4+ T cell. In this study, the authors excluded
triplets where the positive and negative cells have ancestor-descendant 
relationship in the Cell Ontology.

