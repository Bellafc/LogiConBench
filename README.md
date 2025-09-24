# LogiConBench Data Construction

This repository provides the pipeline for constructing the **LogiConBench** dataset, a large-scale benchmark for evaluating logical consistency in LLMs. The dataset contains **280K samples** with $k=2,3,4,5$ statements, automatically generated from symbolic logical graphs and translated into natural language.  

## 🔧 Data Construction Pipeline

The dataset is built through five main steps, each implemented in a corresponding Jupyter notebook:

1. **Generate logical graphs and sample nodes**  
   - Notebook: `step1_generate logical graph and select.ipynb`  
   - Construct logical graphs where nodes are symbolic propositions and edges denote reasoning relations.  
   - Sample subsets of nodes for downstream processing.  

2. **Reorder edges into walk sequences**  
   - Notebook: `step2_reorder.ipynb`  
   - Reorder the edges of sampled nodes into sequential walk structures to ensure consistent reasoning paths.  

3. **Label consistency sets and count inconsistent nodes**  
   - Notebook: `step3_label and count.ipynb`  
   - Assign consistency labels to sampled nodes.  
   - Count how many nodes admit inconsistent sets.  

4. **Rewrite equivalent logical expressions**  
   - Notebook: `step4_rewrite.ipynb`  
   - Apply symbolic rewriting rules to generate multiple logically equivalent variants for each node, enhancing structural diversity.  

5. **Translate into natural language**  
   - Notebook: `step5_nl_template.ipynb`  
   - Convert symbolic expressions into natural language statements using predefined templates and WordNet-based lexical substitutions.  

## 📂 Dataset

- All generated data is stored under the `data/` directory.  
- The dataset includes **280K samples**, distributed across four difficulty levels:  
  - `data/k=2/`  
  - `data/k=3/`  
  - `data/k=4/`  
  - `data/k=5/`  
