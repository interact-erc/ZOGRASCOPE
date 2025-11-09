# ZOGRASCOPE

This is the official repository for the ZOGRASCOPE dataset, you can read the associated paper [here](https://arxiv.org/abs/2503.05268).

The Cypher graph associated to the dataset, where queries can be executed, is the Pole graph available at the official repo [here](https://github.com/neo4j-graph-examples/pole) (we also provide access [here](https://github.com/interact-erc/ZOGRASCOPE/tree/main/graph)).

You can find the code used for the query generation [here](https://github.com/interact-erc/SPOT/tree/main).

The data files, in csv format, contain the following fields: 
- id: id of the sample
- nl: natural language question
- mr: cypher query
- nl_gold_linked: nl with the grounded gold entities included
- nl_bracketed: nl where the text of entities has been replaced
- entities: entities of the nl
- num_nodes: number of nodes
- template_id: template id of the anonymized query
- type: query type
- return_count: number of returns of the query when executed

For the test set we provide two txt files detailing which sample ids belong to the [iid](https://github.com/interact-erc/ZOGRASCOPE/blob/main/data/ids_iid_test.txt) partition and which to the [compositional](https://github.com/interact-erc/ZOGRASCOPE/blob/main/data/ids_compositional_test.txt) partition. For the length partition we provide two separate files containing train and test samples.
We also provide the [schema](https://github.com/interact-erc/ZOGRASCOPE/blob/main/schema/graph_schema.json) of the KG, detailing classes, properties and relations. The dataset is released under the Creative Commons Attribution 4.0 license.

If you use or find our resource useful please cite:
```
@misc{cazzaro2025zograscopenewbenchmarksemantic,
      title={ZOGRASCOPE: A New Benchmark for Semantic Parsing over Property Graphs}, 
      author={Francesco Cazzaro and Justin Kleindienst and Sofia Marquez Gomez and Ariadna Quattoni},
      year={2025},
      eprint={2503.05268},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2503.05268}, 
}
```

### Performance

We present some of the results reported in our benchmark. If you would like to include your results please contact us.
The following table shows results using the nl with information about the grounded entities (nl_gold_linked field in the csv files).

| Model       |   iid   | compositional | length |
|-------------|:-------:|:-------------:|:------:|
| Mistral 7B (fine-tune)     |  97.87%  |     74.97%     | 23.46%  |
| Qwen3 4B (fine-tune)    |  98.04%  |     72.42%     | 20.19%  |
| Llama 3.2-3B (fine-tune)    |  97.90%  |     70.99%     | 25.88%  |
| [SPOT](https://aclanthology.org/2025.findings-acl.524/) (zero-shot)     |  78.38%  |     77.16%     | 66.56%  |
| GPT-4o (zero-shot)     |  41.67%  |     32.91%     | 16.28%  |


