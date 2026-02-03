# 🕵️‍♂️ FatoML - Detecção de Fake News com Machine Learning

> Aplicação Web e API para análise de veracidade de notícias utilizando Processamento de Linguagem Natural (NLP) e múltiplos modelos de Classificação.

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_Framework-red?style=for-the-badge&logo=flask&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/ML-Scikit_Learn-orange?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Data_Science-Notebooks-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

## 🎯 Sobre o Projeto
O **FatoML** é uma ferramenta desenvolvida para auxiliar no combate à desinformação. O sistema recebe um texto de notícia e o submete a **5 algoritmos de Machine Learning** diferentes simultaneamente, retornando a classificação (Falso/Verdadeiro) de cada um para maior confiabilidade.

Este projeto faz parte do portfólio de Ciência da Computação, demonstrando o ciclo completo de Ciência de Dados: desde a Análise Exploratória (EDA) até o deploy do modelo em uma aplicação web.

## 🧠 Modelos Implementados
O sistema utiliza os seguintes algoritmos treinados (serializados em `.pkl`):
* **RFC:** Random Forest Classifier
* **DTC:** Decision Tree Classifier
* **LR:** Logistic Regression
* **LSVC:** Linear Support Vector Classifier
* **PAC:** Passive Aggressive Classifier

## 📂 Estrutura do Projeto

```text
FatoML_API/
├── modelos/          # Arquivos .pkl (Modelos treinados e Vetorizadores)
├── static/           # Arquivos estáticos (Imagens, CSS, JS)
├── templates/        # Frontend (index.html)
├── App.py            # API Backend (Flask)
├── Analise_Exploratoria_Fake_News.ipynb  # Notebook de EDA e Limpeza
└── Analise_Resultados_Fake_News.ipynb    # Notebook de Treinamento e Testes
```

## 🚀 Como Rodar
* **Pré-requisitos**
Certifique-se de ter o **Python** instalado. Instale as dependências necessárias:
```Bash
pip install flask scikit-learn joblib pandas
```

* **Executando a Aplicação**
No terminal, execute o arquivo principal:
```Bash
python App.py
```
O navegador abrirá automaticamente em http://127.0.0.1:5000.

## 🔌 Documentação da API
A aplicação possui um endpoint RESTful que pode ser consumido por outros sistemas.

POST /prever
Recebe um texto e retorna a classificação de todos os modelos.

* Request Body (JSON):
```JSON
{
  "texto": "O governo anunciou hoje uma nova medida provisória..."
}
```

* Response (JSON): 0 indica Fake News / 1 indica Notícia Real (exemplo)
```JSON
{
  "rfc": 1,
  "dtc": 0,
  "logreg": 1,
  "svc": 1,
  "pac": 1
}
```

## 🛠️ Tecnologias Utilizadas
* Backend: Python, Flask.
* Machine Learning: Scikit-Learn, Joblib.
* Frontend: HTML5, CSS3.
* Análise de Dados: Pandas, Jupyter Notebook.

Desenvolvido por GuiRibCarra.
