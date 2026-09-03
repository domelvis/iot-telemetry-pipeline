# iot-telemetry-pipeline
Pipeline de ingestão, tratamento e análise exploratória de séries temporais de sensores IoT (DHT22) via API REST.
# 📡 IoT & Data Science Telemetry Pipeline

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![IoT](https://img.shields.io/badge/IoT-Konker%20Labs-orange)
![License](https://img.shields.io/badge/License-MIT-green)

Pipeline completa de ingestão, normalização, tratamento e visualização de séries temporais geradas por sensores climáticos IoT (**DHT22**) distribuídos em polos educacionais (projeto baseado no laboratório prático da Univesp com a plataforma Konker Labs).

---

## 📌 Visão Geral da Arquitetura

O ecossistema foi desenhado para coletar eventos contínuos de dispositivos embarcados e transformá-los em insumos estatísticos para análise exploratória de dados:

1. **Camada de Dispositivos (Edge/IoT):** Sensores de temperatura e umidade relativa (DHT22) conectados à rede enviando telemetria e dados de conectividade.
2. **Camada de Ingestão (API REST / OAuth2):** Interface de autenticação segura baseada em protocolo OAuth2 (Client Credentials) consumindo endpoints de eventos da plataforma Konker.
3. **Camada de Transformação (ETL):** Normalização de cargas semiestruturadas (JSON aninhado), segregação por canais lógicos e ajuste temporal com fuso horário local (`America/Sao_Paulo`).
4. **Camada Analítica & Visualização:** Estatística descritiva, correlação cruzada entre variáveis físicas e geração de gráficos com eixos independentes.

---

## 🛠️ Tecnologias e Bibliotecas Utilizadas

| Ferramenta / Biblioteca | Função Técnica no Projeto |
| :--- | :--- |
| **Google Colab** | Ambiente em nuvem para prototipação, experimentação e execução iterativa |
| **Python 3.x** | Linguagem principal para scripts de pipeline e análise de dados |
| **Requests-OAuthlib / OAuthlib** | Gerenciamento do fluxo de autenticação OAuth2 e aquisição de Access Token |
| **Pandas** | Manipulação de DataFrames, normalização de JSON e agregações temporais |
| **NumPy** | Operações numéricas vetorizadas e simulação estocástica de séries temporais |
| **Arrow** | Manipulação robusta de datas, timestamps ISO-8601 e fusos horários |
| **Matplotlib** | Construção de gráficos temporais de eixos duplos (`twinx`) e customização visual |
| **Seaborn** | Visualização de dispersão estatística e linhas de regressão linear |
| **Git / GitHub** | Controle de versão e publicação remota via Personal Access Token (PAT) |

---

## 📁 Estrutura de Diretórios Recomendada

```text
iot-telemetry-pipeline/
├── data/
│   └── sensor_data_sample.csv       # Amostra exportada dos dados processados
├── notebooks/
│   └── iot_telemetry_analysis.ipynb # Notebook executado no Google Colab
├── img/
│   └── telemetry_chart.png          # Visualização gerada do gráfico duplo
├── .gitignore                       # Ignora arquivos temporários e checkpoints
├── requirements.txt                 # Dependências do ecossistema Python
└── README.md                        # Documentação técnica do projeto
