# Graph Contrastive Learning with Positional Representation for Recommendation

This repository contains Pytorch codes and datasets for the paper:
> Zixuan Yi, Iadh Ounis and Craig MacDonald (2023). Graph Contrastive Learning with Positional Representation for Recommendation. In ECIR'23, Dublin, Ireland, April 2-6, 2023.

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
* Configure the xx.conf file in the directory named conf. (xx is the name of the model you want to run)</li>
* Run main.py and choose the model you want to run.</li>


## Datasets
Three datasets are adopted to evaluate PGCL: <i> Yelp, Gowalla, </i>and <i>Amazon-Kindle</i>. The user-item pair $(u_i, v_j)$ in the adjacent matrix is set as 1, if user $u_i$ has rated item $v_j$ in Yelp, or if user $u_i$ has check in venue $v_j$ in Gowalla, or if user $u_i$ has purchased item $v_j$ in Amazon-Kindle. We filtered out users and items with too few interactions.

## How to Run the Codes
Will upload the instructions recently.


