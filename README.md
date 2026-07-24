# 🔧 PulseGuard — Manutenção Preditiva com Dados de Sensores IoT

Predição de falhas em equipamentos industriais a partir de dados de sensores IoT (vibração, acústico, temperatura, corrente) através de análise exploratória de dados e machine learning.

## 📌 Visão Geral

Paradas não planejadas de equipamentos são um dos problemas mais custosos em operações industriais. Este projeto explora um dataset de sensores IoT para entender o comportamento de máquinas antes de eventos de falha, com o objetivo de construir um modelo preditivo capaz de identificar anomalias antes que causem quebras.

## 🎯 Objetivo

- Explorar e entender os dados de sensores IoT coletados de máquinas industriais
- Identificar padrões nas leituras dos sensores (vibração, acústico, temperatura, corrente) que antecedem falhas
- Construir um modelo de machine learning para prever falhas de equipamento (`label` = 1)

## 📊 Dataset

- **Fonte:** [IoT-Integrated Predictive Maintenance Dataset (Kaggle)](https://www.kaggle.com/datasets/ziya07/iot-integrated-predictive-maintenance-dataset/data)
- **Tamanho:** 1.800 registros, 10 colunas
- **Features:** `vibration`, `acoustic`, `temperature`, `current`, e componentes derivados do sinal (`IMF_1`, `IMF_2`, `IMF_3`)
- **Variável-alvo:** `label` (0 = operação normal, 1 = falha) — dataset desbalanceado (~11% de falhas)

## 🛠️ Tecnologias

- Python
- Pandas, NumPy
- Seaborn, Matplotlib
- Jupyter Notebook
- Scikit-learn *(próxima fase)*

## 📁 Estrutura do Projeto

PulseGuard/
├── data/ # Datasets brutos e processados
├── notebooks/
│ └── 01_eda.ipynb # Análise Exploratória de Dados
├── src/ # Módulos Python reutilizáveis
├── README.md
└── requirements.txt


## 🔍 Principais Descobertas (EDA)

- Nenhum valor ausente em todo o dataset
- Leituras dos sensores mostram picos irregulares frequentes, consistentes com eventos mecânicos transitórios
- `vibration` e `acoustic` apresentam a maior variabilidade relativa entre os sensores
- Variável-alvo desbalanceada (~11% de falhas), exigindo cuidado na modelagem (ex: ponderação de classes, métricas como F1/AUC-PR em vez de acurácia)



## 🚀 Próximos Passos

- [ ] Engenharia de atributos (estatísticas móveis, análise de correlação)
- [ ] Treinamento e avaliação de modelos de classificação
- [ ] Interpretabilidade do modelo (SHAP / importância de features)
- [ ] Deploy como demo de predição simples

## ▶️ Como Rodar

```bash
git clone https://github.com/agnaldo-gonzaga/PulseGuard.git
cd PulseGuard
python -m venv venv
venv\Scripts\activate       # Windows
pip install -r requirements.txt
jupyter notebook notebooks/01_eda.ipynb
```

## 👤 Autor

**Agnaldo Gonzaga**
[LinkedIn](#) | [GitHub](https://github.com/agnaldo-gonzaga)