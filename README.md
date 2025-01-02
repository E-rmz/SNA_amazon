# Amazon Product Co-Purchasing Network Analysis

This project focuses on analyzing Amazon's co-purchasing network metadata to understand the connections between products and customer behaviors. Using graph-based techniques, we created primary networks and subgraphs to explore customer-product and product-product relationships. The project leverages publicly available datasets and tools for social network analysis to derive actionable insights.

---

## Project Overview

### **1. Dataset**
The dataset used in this project was compiled by **Jure Leskovec**, **Lada A. Adamic**, and **Bernardo A. Huberman** during the summer of 2006 as part of their study on viral marketing dynamics. It is available through the [Stanford Network Analysis Project (SNAP)](https://snap.stanford.edu/data/amazon-meta.html). The dataset includes:
- **548,552 products**, such as books, music CDs, DVDs, and VHS tapes.
- Attributes such as:
  - Title
  - Sales rank
  - Product categories
  - Similar products
  - Detailed customer reviews (time, ID, rating, votes, helpfulness).

This dataset provides the foundation for creating customer-product and product-product networks.

---

### **2. Key Steps**
1. **Primary Network Construction**:
   - A primary customer-product network was constructed using the `primary_network_construction.ipynb` file.
   - This includes over 2.5 million nodes and 8 million edges, representing customers and products and their interactions.
   
2. **Subgraph Creation**:
   - Due to the computational complexity of analyzing the entire network, we focused on smaller subgraphs.
   - The subgraph creation process is documented in the `Subgraph_Analysis.ipynb` file.
   - The final subgraph contains approximately 1,000 nodes and preserves key characteristics of the primary network.

3. **Reproducibility**:
   - To ensure reproducibility, the generated subgraph is included in this repository (`final_subgraph.pkl`).

---

### **3. Methodology**
- **Customer-Product Network**:
  - Nodes represent customers and products.
  - Edges connect customers to products they reviewed or purchased.
  - Edge attributes include review weight, rating, and timestamps.

- **Product-Product Network**:
  - Nodes represent products.
  - Edges connect products identified as "similar" in the dataset.
  - Attributes include average product ratings.

- **Subgraph Construction**:
  - A representative subgraph was extracted using breadth-first search (BFS) from seed nodes selected based on degree centrality and product categories.
  - The subgraph preserves key properties such as community structures and local dynamics.

---

### **4. Tools and Libraries**
The project was developed using Python and the following libraries:
- **NetworkX**: For graph creation and analysis.
- **Pandas**: For data preprocessing and tabular analysis.
- **Scikit-learn**: For clustering algorithms.
- **Matplotlib/Seaborn**: For data visualization.
- **Community Detection Package**: For community-based analyses.

---

## Citation
If you use this dataset or methodology, please cite:
- **J. Leskovec, L. Adamic, and B. Huberman**: *The Dynamics of Viral Marketing*. ACM Transactions on the Web (TWEB), 1(1), 2007.  
- Dataset: [Amazon Meta-Data](https://snap.stanford.edu/data/amazon-meta.html)

---

