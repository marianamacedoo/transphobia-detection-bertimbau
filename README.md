# Detecção de Discurso Transfóbico na Rede Social X com BERTimbau

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/)
[![HuggingFace](https://img.shields.io/badge/🤗-Transformers-orange.svg)](https://huggingface.co/neuralmind/bert-base-portuguese-cased)

Repositório oficial do projeto que utiliza redes neurais BERT para identificação de discurso de ódio transfóbico na plataforma X (Twitter). Este trabalho foi desenvolvido como parte do conteúdo programático da disciplina Redes Neurais e Aprendizagem em Profundidade, ministrada pelos professores Pedro Silva e Eduardo Luz, do Departamento de Computação da UFOP.

## 📄 Resumo
Implementação de um modelo BERTimbau fine-tuned para classificação de tweets em **transfóbicos** (1) ou **não transfóbicos** (0). O modelo alcançou **93.1% de acurácia** em um conjunto de validação balanceado, demonstrando eficácia na detecção de padrões linguísticos complexos associados à transfobia.

## 📂 Estrutura do Repositório
```
transfobia-detection-bertimbau/
├── code/
│   └── ProjetoBCC406.ipynb          # Notebook com implementação completa
├── data/
│   └── dados_rotulados.csv          # Dataset de 144 tweets rotulados manualmente
├── docs/
│   └── Artigo_Redes_Neurais.pdf     # Artigo científico detalhando a pesquisa
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## 🔧 Requisitos e Instalação
```bash
git clone https://github.com/luizelemesmo/transfobia-detection-bertimbau.git
cd transfobia-detection-bertimbau
pip install -r requirements.txt
```

## 📊 Dataset
**Características principais:**
- Coletado via API oficial do X (Twitter)
- 144 tweets em português brasileiro
- Pré-processado (remoção de URLs, menções e espaços extras)
- Distribuição de classes:
  | Classe | Descrição           | Quantidade |
  |--------|---------------------|------------|
  | 0      | Não transfóbico     | 62         |
  | 1      | Transfóbico         | 82         |

**Acesso:** `data/dados_rotulados.csv`

## 🧠 Metodologia
1. **Pré-processamento:** Limpeza de textos com regex
2. **Tokenização:** BERTimbau (português) com máximo de 128 tokens
3. **Modelagem:** Fine-tuning do BERT com:
   - Otimizador Adam (lr=2e-5)
   - Batch size=16
   - 20 épocas
4. **Avaliação:** Métricas em conjunto de validação (20% dos dados)

## 📈 Resultados
| Métrica       | Validação |
|---------------|-----------|
| Acurácia      | 93.10%    |
| Precisão      | 100.00%   |
| Recall        | 89.47%    |
| F1-Score      | 94.44%    |

## 💻 Como Utilizar
**Classificação de novos textos:**
```python
from predict import predict  # Função customizada do notebook

texto = "Exemplo de texto potencialmente ofensivo"
print(predict(texto))  # Retorna 'Transfobia' ou 'Não transfobia'
```

**Reprodução completa:**
1. Executar todas as células do Jupyter Notebook `code/ProjetoBCC406.ipynb`
2. Ajustar caminhos para o dataset conforme necessário

## ⚠️ Considerações Éticas
1. **Dados Sensíveis:** Contém textos potencialmente ofensivos - uso restrito a pesquisa
2. **Vieses:** Modelo treinado em amostra específica - requer validação externa
3. **Responsabilidade:** Não utilizar para moderação automática sem revisão humana

## 📚 Referências
- [BERTimbau Base](https://huggingface.co/neuralmind/bert-base-portuguese-cased)
- [Artigo Completo](https://github.com/luizelemesmo/transphobia-detection-bertimbau/blob/fa5d3456e7a4434954fc054ba8b5a710173c6bba/docs/Artigo%20-%20Luiz%20H.%20Carvalho%20%26%20Mariana%20Macedo.pdf)

## Licença
Este projeto é licenciado sob a [MIT License](LICENSE) - consulte o arquivo para detalhes.
