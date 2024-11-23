# CausalGeneAnalysis

## Objective

Exploring Gene Causality.

## Introduction

Phenotypes are traits or conditions that we can observe in an individual, which are influenced by genes. A causal gene is one that directly influences the development of a trait or disease.

Variations in this gene can result in observable changes in the phenotype, making it a key target for genetic studies. Figuring out which genes are causal (for a particular phenotype) from many possible candidates is essential in fields like medicine, genetics, and biology. This knowledge helps in creating specific treatments and diagnostics by understanding the genetic foundations of different traits and conditions.

#### Now, what makes a gene causal?

Numerous researchers have pursued this question and published their findings in literature. Literature, which is accessible to us, has also been used to train Large Language Models like Open AI's and Meta's GPT and Llama respectively. It's plausible that these models, when asked about specific phenotypes or genes, generate embeddings that reflect the literature's consensus on their genetic associations.

## Problem to be Solved

Dataset consists of phenotypes, embeddings for the list of phenotypes and their corresponding causal genes. These embeddings were created by asking GPT3.5 to describe the gene or phenotype, and embeddings them using Open AI's text-embedding-3-large model. So, the embeddings for each phenotype and gene contain detailed information about their characteristics. **So task is to conduct an Exploratory Analysis to determine if these embeddings might indicate gene causality.** In other words, does a pair of phenotype embedding and gene embedding give any signal for causality?

## About Dataset

The dataset is hosted on Zenodo.org and can be downloaded from [here](https://zenodo.org/records/11391053). We will only use the files that are specified below for the analysis.
* **Phenotypes and Genes**: A trait or condition, with associated genes. Out of these, only one gene is causal.

    File: ```zenodo_directory/data/benchmark_datasets/opentargets_step2.for_llm.tsv```

* **Ground Truth**: The gene considered causal for the phenotype. The ordering in this file is consistent with the above file.

    File: ```zenodo_directory/data/benchmark_datasets/opentargets_step2.labels```

* **Features**: 3072-dimensional embeddings vector for all phenotypes and all genes. These are the features we need for the analysis.

    File1: ```zenodo_directory/data/helper_dataset/gene_embeddings.csv```
    
    File2: ```zenodo_directory/data/helper_dataset/phenotype_embeddings.csv```

### Using a Unique Subset:

To ensure that we work with a unique subset of the data, we will use a sample string (in this project I used my name as a sample string), and create a hash value as seed for random sampling.

## Task

Our Task is to conduct an Exploratory Analysis to determine if these embeddings might indicate gene causality.

* **Mapping of Phenotypes to Genes**: 

    Each phenotype is associated with mulitple genes, one being causal and the rest, non-causal.

    Here, we will map one phenotype to its causal gene and also to several non-causal genes, labeling the pair as causal and non-causal respectively.

* **Dimensionality Reduction**:

    We will apply suitable methods to reduce the dimensions of the embedding vectors to facilitate visualization of the relationships between phenotype and gene embeddings.

* **Vector Analysis**:

    We will manipulatee the embeddings to derive new vectors that may represent the relationships between genes and phenotypes and analyze these derived vectors to explore potential insights into causality.

* **Clustering**:

    We will implement different unsupervised methods to cluster the embeddings and analyze these clusters to identify distinct patterns or groups that suggests causal relationships between genes and phenotypes.