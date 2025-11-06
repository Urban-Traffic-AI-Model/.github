# 🧠 Urban Traffic AI Model  
> Previsão de volume de tráfego urbano com aprendizado supervisionado e redes neurais MLP  

---

## 📌 Visão Geral  

O **Urban Traffic AI Model** é um projeto acadêmico que aplica conceitos de **aprendizado supervisionado** e **redes neurais multicamadas (MLP)** para prever o volume de tráfego em vias urbanas, utilizando o dataset público **[Metro Interstate Traffic Volume](https://archive.ics.uci.edu/dataset/492/metro+interstate+traffic+volume)** ou **[Kaggle](https://www.kaggle.com/code/ramyahr/metro-interstate-traffic-volume)**.  


O objetivo é compreender como **condições climáticas, datas e feriados** influenciam o tráfego em uma rodovia metropolitana, transformando dados brutos em predições úteis por meio de um pipeline estruturado em camadas.  

---

## 🏗️ Arquitetura do Projeto (Medallion Architecture)  

### 🥉 **Camada Bronze — Dados Brutos**  
Armazena o dataset original, sem modificações.  
- Fonte:  **[Metro Interstate Traffic Volume](https://archive.ics.uci.edu/dataset/492/metro+interstate+traffic+volume)** ou **[Kaggle](https://www.kaggle.com/code/ramyahr/metro-interstate-traffic-volume)**
- Arquivo: `data/01_bronze/Metro_Interstate_Traffic_Volume.csv`  

### 🥈 **Camada Silver — Limpeza e Padronização**  
Tratamento e normalização dos dados:  
- Remoção de valores nulos e outliers  
- Conversão da data em variáveis de tempo (ano, mês, hora, dia da semana)  
- Codificação de variáveis categóricas com *One-Hot Encoding*  
- Normalização de atributos numéricos com *StandardScaler*  

### 🥇 **Camada Gold — Feature Engineering**  
Criação de novas variáveis para melhorar o desempenho do modelo:  
- Indicadores de horários de pico  
- Classificação de climas extremos  
- Identificação de feriados prolongados  

### 🤖 **Modelagem — Rede Neural Multicamadas (MLP)**  
Treinamento de um modelo de rede neural usando *TensorFlow/Keras*:  
- 3 camadas ocultas  
- Funções de ativação: **ReLU** e **Sigmoid**  
- Ajuste de *learning rate*, *epochs* e *batch size*  
- Avaliação com métricas: **MAE** e **R²**

---

## 📚 Estrutura de Diretórios  

```bash
urban_traffic_ai_model/
│
├─ data/
│   ├─ 01_bronze/           # Dados brutos
│   ├─ 02_silver/           # Dados limpos e normalizados
│   │   ├─ dataset-real/
│   │   └─ dataset-teste/
│   └─ 03_gold/             # Dataset final para modelagem
│
├─ models/                  # Modelos treinados (MLP)
├─ notebooks/               # Experimentos e análises
├─ reports/                 # Relatórios técnicos
├─ src/                     # Código principal do projeto
└─ requirements.txt          # Dependências do ambiente
```
---

## ⚙️ Principais Tecnologias
Categoria |	Biblioteca |	Função Principal	| Documentação
|----------|----------|----------|----------|
Análise de dados |	pandas	| Manipulação e limpeza de dados tabulares |	pandas.pydata.org
Numérico e estatístico |	numpy |	Operações matemáticas e vetorização	| numpy.org
Machine Learning / Deep Learning |	tensorflow, keras |	Implementação da rede neural MLP |	tensorflow.org
Visualização |	matplotlib, seaborn |	Gráficos de correlação, perda e acurácia |	matplotlib.org
Pré-processamento	| scikit-learn |	Normalização e codificação de variáveis	| scikit-learn.org
Ambiente |	python-dotenv	| Gerenciar variáveis de ambiente (opcional)|	pypi.org/project/python-dotenv

---

## 🖥️ Execução
Clone o repositório:

```cmd
git clone https://github.com/Urban-Traffic-AI-Model/urban_traffic_ai_model_mlp.git #Clone o repositório
cd urban_traffic_ai_model #Entre dentro do projeto
pip install -r requirements.txt #Instale as dependencias
jupyter notebook data/02_silver/dataset-real/clean_data_real.ipynb #Execute as limpezas no dataset real
python src/train_mlp.py #Treine o modelo
```
---

## 📊 Métricas Esperadas
MAE (Mean Absolute Error): erro médio absoluto da previsão de volume de tráfego

R² (Coeficiente de Determinação): qualidade do ajuste do modelo

Loss / Accuracy plots: gráficos de desempenho por época de treinamento

---

<div align="center">

## ✍️ Autores
| Nome/LinkedIn |
|---------------|
| 👨‍💻 [Kleber Ludorf](https://www.linkedin.com/in/kl%C3%A9ber-ludorf-84710631b/) |
| 👨‍💻 [Pedro Santos](https://www.linkedin.com/in/pedro-henrique-santos-silva) |

</div>

---
🧭 Licença
Este projeto é de uso acadêmico e segue as normas de citação e integridade científica da instituição.
