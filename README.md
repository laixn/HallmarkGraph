## HallmarkGraph: a cancer hallmark informed graph neural network for classifying hierarchical tumor subtypes
[![Static Badge](https://img.shields.io/badge/JOURNAL-bioinformatics-blue)](https://doi.org/10.1093/bioinformatics/btaf44)
[![Static Badge](https://img.shields.io/badge/PDF-researchgate-green)](https://www.researchgate.net/publication/394474215_HallmarkGraph_a_cancer_hallmark_informed_graph_neural_network_for_classifying_hierarchical_tumor_subtypes)
[![Static Badge](https://img.shields.io/badge/ZENODO-10.5281/zenodo.15790123-red)](https://zenodo.org/records/15790123)

We present a graph neural network, HallmarkGraph, the first biologically informed model developed to classify hierarchical tumor subtypes in human cancer. Inspired by cancer hallmarks, the model’s architecture integrates transcriptome profiles and gene regulatory interactions to perform multi-label classification. We evaluate the model on a comprehensive pan-cancer cohort comprising 11,476 samples from 26 primary cancers with 405 subtypes. 

![hallmarkgraph](https://github.com/user-attachments/assets/7f0689d0-99b0-4486-9caf-552ed20bbb20)

## The current version is to provide reviewers with reproducible experimental results
The repository contains the following strucutre and files:
```bash
main/
  └──code/ # the code to run the model
        └── HallmarkGraph.py
  └──data/ # the data used to train and test the model
        ├── clean_data.csv
        ├── clean_label.xlsx
        └── model_validation.xlsx
  └──adjacency_matrix/ # the cancer hallmark matrix for GCN
        ├── Undirected_0...matrix.npz
        ├── ...
        └── Undirected_9...matrix.npz
  └──best_model/ # the best model we reported in the paper
        ├── my_BioGCN_net_(0.4)_target_1.h5
        ├── ...
        └── my_BioGCN_net_(0.4)_target_8.h5
```

## Pre-requisites: 
* Linux (Ubuntu 18.04) 
* NVIDIA GPU (Nvidia GeForce RTX 2080 Ti x 2)
* Python (3.8), tensorflow (2.8.2), keras (2.8.0), shap (0.45.1), scikit-learn (1.4.1), matplotlib (3.9.2)    

## How to reproduce the results:
1. You first need to download the archived data and models from [![Static Badge](https://img.shields.io/badge/ZENODO-grey)](https://zenodo.org/records/15790123) and store them in `data` and `best_model` folders, respectively (see readme.md in the folder).
2. Run the file `code/HallmarkGraph.py`
3. If you want to predict hard samples (i.e., validation data), please set `Whether_to_predict_hard_stamples = TRUE` in `code/HallmarkGraph.py`. The curated, finalized results can be found in `data/model_validation.xlsx`
4. If you want to calculate the SHAP values, please set `Whether_to_calculate_the_shap = TRUE` in `code/HallmarkGraph.py`.

## Usage & Citation 
If you find our work useful, please consider citing it:

Qingsong Zhang, Fei Liu, Xin Lai. HallmarkGraph: a cancer hallmark informed graph neural network for classifying hierarchical tumor subtypes. 
Bioinformatics. https://doi.org/10.1093/bioinformatics/btaf444 (2025).

```bash
@article{Zhang_Hallmarkgraph_2025,
  title={HallmarkGraph: a cancer hallmark informed graph neural network for classifying hierarchical tumor subtypes},
  author={Qingsong Zhang, Fei Liu, Xin Lai},
  journal={Bioinformatics},
  doi={10.1093/bioinformatics/btaf444},
  year={2025}
}
```


© [Lai Lab](https://sites.google.com/view/lai-lab) - This code is made available under the GPLv3 License and is available for non-commercial academic purposes.
```
