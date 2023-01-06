# Graph Contrastive Learning with Positional Representation for Recommendation

This repository contains Pytorch codes and datasets for the paper:
> Zixuan Yi, Iadh Ounis and Craig MacDonald (2023). Graph Contrastive Learning with Positional Representation for Recommendation. In ECIR'23, Dublin, Ireland, April 2-6, 2023.

## Introduction
This paper proposed a hypergraph transformer model named SHT to tackle the data sparsity and noise problem in collaborative filtering. It combines user/item id embedding with the topology-aware embedding given by GCNs as the local view, and learns the latent global relations in a transformer-like hypergraph encoder. The local embeddings are then denoised by the global view using an augmented solidity differentiation task. Comparing to our previous work <a href='https://github.com/akaxlh/HCCF'>HCCF</a> which is on hypergraph contrastive learning for CF, this paper proposes the novel hypergraph transformer architecture with the self-augmented solidity differentiation task, and highlights the strength of generative self-supervised learning.

## Citation
If you want to use our codes and datasets in your research, please cite:
```
@inproceedings{yi2023graph,
  title={Graph Contrastive Learning with Positional Representation for Recommendation},
  author={Yi,Zixuan and Ounis, Iadh and Macdonald, Craig},
  booktitle={European Conference on Information Retrieval},
  year={2023},
  organization={Springer}
}

```

## Environment
The codes of PGCL are implemented and tested under the following development environment:
* numba==0.53.1
* numpy==1.20.3
* scipy==1.6.2
* torch>=1.7.0


## Usage
*Configure the xx.conf file in the directory named conf. (xx is the name of the model you want to run)</li>
*Run main.py and choose the model you want to run.</li>


## Datasets
Three datasets are adopted to evaluate PGCL: <i> Yelp, Gowalla, </i>and <i>Amazon-Kindle</i>. The user-item pair $(u_i, v_j)$ in the adjacent matrix is set as 1, if user $u_i$ has rated item $v_j$ in Yelp, or if user $u_i$ has check in venue $v_j$ in Gowalla, or if user $u_i$ has purchased item $v_j$ in Amazon-Kindle. We filtered out users and items with too few interactions.

## How to Run the Codes
Please unzip the datasets first. Also you need to create the `Models/` directory. The following command lines start training and testing on the three datasets, respectively, which also specify the hyperparameter settings for the reported results in the paper. Training and testing logs for trained models are contained in the `History/` directory.


```
Important arguments:
* `reg`: This is the weight for weight-decay regularization. Empirically recommended tuning range is `{1e-2, 1e-3, 1e-4, 1e-5}`.
* `ssl_reg`: This is the weight for the solidity prediction loss of self-supervised learning task. The value is tuned from `{1e-3, 1e-4, 1e-5, 1e-6, 1e-7}`.
* `mult`: This hyperparameter is to emplify the ssl loss for better performance, which is tuned from `{16, 64, 1e1, 1e2, 1e3}`.
* `edgeSampRate`: This parameter determines the ratio of edges to conduct the solidity differentiation task on. It should be balanced to consider both model performance and training efficiency.

## Achnowledgements
This research work is supported by the research grants from the Department of Computer Science & Musketeers Foundation Institute of Data Science at the University of Hong Kong.
