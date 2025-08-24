# OOD-SEIB
Graph Out-of-Distribution Generalization based on Structural Entropy guided Information Bottleneck


## Project Overview
`Abstract` Out-of-Distribution (OOD) generalization is a promising yet challenging goal that guarantees the testing performance of Graph Neural Networks (GNNs) in open-world settings. However, due to the variability of graph structure, redundant information from the spurious topologies severely confuse the GNN to deviate from the target label. Hence, capturing the label-relevant subgraph topologies from the original graphs can alleviate this problem. Unfortunately, existing works fail to dynamically characterize the subgraph structural information due to the ignorance of global structural distribution or reliance on pre-assigned structural distributions. To this end, we propose Graph Out-of-Distribution Generalization based on <u>S</u>tructural <u>E</u>ntropy guided <u>I</u>nformation <u>B</u>ottleneck, which named **OOD-SEIB**. Specifically, we first propose concise topology extraction module to assign importance scores on edges. Within it, to characterize the mutual information between input graph and extracted subgraph at the topological level, we dynamically quantify it based on structural entropy, termed the conciseness index. Secondly, to capture stable and invariant subgraph topologies, we propose the structural information bottleneck compression module to jointly optimize conciseness index and label-relevance of the extracted subgraph, trading off the informativeness and compression. Finally, to further enhance adaptability in unobserved environments, OOD-SEIB generates multi-factors to simulate various augmented environments, and distills the invariant topology knowledge into the GNN. Extensive experiments on both synthetic and real datasets with distribution shift confirm the effectiveness of our OOD-SEIB.  Our code is availiable at [Anonymous Github](https://anonymous.4open.science/r/OOD-SEIB-1C51).

![overall framework](figures/overall_framework.png)


## Dependancy
PYTHON 3.8, PyTorch 2.0.0, PyTorch Geometric 2.5.3

## Datasets
You can make directories `./data/Graph_level` and `./data/Node_level` respectively, and download the datasets through the Google drive:
```
https://drive.google.com/drive/folders/1eV5mb115htuzRusWWqPUECPNwyNg888S
```

## Running the code
We provide the optimal trained model in the `./checkpoint`, you can test OOD-SEIB in `./test`. 

Or you can train the OOD-SEIB from scratch, please refer to the bash script `run.sh` in `./Graph_level` and `./Node_level`.
