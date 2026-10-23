Transphobic Speech Detection on Social Network X Using BERTimbau

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg) ![Python 3.11](https://img.shields.io/badge/Python-3.11-blue.svg) ![HuggingFace](https://img.shields.io/badge/🤗-Transformers-orange.svg)

Official repository for the project that uses BERT neural networks to identify transphobic hate speech on the X (Twitter) platform. This work was developed as part of the Neural Networks and Deep Learning course, taught by professors Pedro Silva and Eduardo Luz at the Department of Computing of the Federal University of Ouro Preto (UFOP), Brazil.

📄 Abstract

Implementation of a fine-tuned BERTimbau model for classifying tweets as transphobic (1) or non-transphobic (0). The model achieved 93.1% accuracy on a balanced validation set, demonstrating its effectiveness in detecting complex linguistic patterns associated with transphobia.

📂 Repository Structure
transphobia-detection-bertimbau/
├── code/
│   └── ProjetoBCC406.ipynb          # Notebook with the complete implementation
├── data/
│   └── dados_rotulados.csv          # Dataset of 144 manually labeled tweets
├── docs/
│   └── Artigo_Redes_Neurais.pdf     # Research paper detailing the study
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt

🔧 Requirements and Installation
git clone https://github.com/luizelemesmo/transfobia-detection-bertimbau.git
cd transfobia-detection-bertimbau
pip install -r requirements.txt

📊 Dataset

Key characteristics:

Collected through the official X (Twitter) API
144 tweets in Brazilian Portuguese
Preprocessed by removing URLs, mentions, and extra whitespace
Class distribution:
Class	Description	Count
0	Non-transphobic	62
1	Transphobic	82

Access: data/dados_rotulados.csv

🧠 Methodology
Preprocessing: Text cleaning using regular expressions (regex).
Tokenization: BERTimbau (Portuguese) with a maximum sequence length of 128 tokens.
Modeling: BERT fine-tuning with the following hyperparameters:
Optimizer: Adam (lr=2e-5)
Batch size: 16
Number of epochs: 20
Evaluation: Metrics computed on a validation set comprising 20% of the data.
📈 Results
Metric	Validation
Accuracy	93.10%
Precision	100.00%
Recall	89.47%
F1-score	94.44%
💻 How to Use

Classifying new texts:

from predict import predict  # Custom function from the notebook

text = "Example of potentially offensive text"
print(predict(text))  # Returns 'Transphobia' or 'No transphobia'


Reproducing the experiment:

Run all cells in the Jupyter Notebook code/ProjetoBCC406.ipynb.
Adjust the dataset paths as needed.
⚠️ Ethical Considerations
Sensitive Data: Contains potentially offensive text and should be used for research purposes only.
Biases: The model was trained on a specific sample and requires external validation.
Responsibility: Do not use the model for automated content moderation without human review.
📚 References
BERTimbau Base
Full Research Paper


