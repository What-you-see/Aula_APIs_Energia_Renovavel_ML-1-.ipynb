# Projeto de Classificação e Regressão - Machine Learning

## 🎯 Objetivo
Este projeto tem como objetivo aplicar algoritmos de Machine Learning em dois problemas distintos:
1. **Tarefa 1 (Classificação):** Prever a fonte de energia de uma infraestrutura (Solar, Eólica ou Hídrica) com base na sua localização (latitude/longitude) e potência outorgada.
2. **Tarefa 2 (Regressão):** Estimar a radiação solar global horizontal média com base em condições meteorológicas e na hora local.

## 📊 Fontes e Período dos Dados
* **Tarefa 1:** Dados públicos provenientes do sistema SIGA da ANEEL, representando o estado atual das centrais geradoras.
* **Tarefa 2:** Dados históricos meteorológicos obtidos através da API pública Open-Meteo para a cidade de Petrolina (PE). O período analisado compreende entre **1 de abril de 2025 e 30 de junho de 2025**.

## 🚀 Instruções para Executar o Notebook
1. Certifique-se de que tem os ficheiros `.csv` presentes neste repositório ou permita que o *notebook* faça as consultas às APIs para os gerar automaticamente.
2. Pode abrir o ficheiro `.ipynb` localmente utilizando o Jupyter Notebook/Lab ou através da nuvem no **Google Colab**.
3. No Google Colab, vá a `Ambiente de execução` (Runtime) e selecione `Reiniciar sessão e executar tudo` (Restart and run all) para executar as células na ordem correta, a partir de um ambiente limpo.
4. As seis comparações (três classificadores e três regressores) e as respostas discursivas encontram-se estruturadas sequencialmente ao longo do ficheiro.

## 📈 Resumo dos Resultados
* **Tarefa 1 (Classificação):** Foram testados os modelos KNN, Regressão Logística e Random Forest. O **Random Forest** obteve o melhor desempenho na separação das classes, alcançando uma Accuracy e um F1-Score (Macro) na ordem dos 97,5%. O modelo demonstrou que a Regressão Logística é insuficiente para este problema por não capturar as não-linearidades geográficas.
* **Tarefa 2 (Regressão):** Foram avaliados modelos de Regressão Linear, Árvore de Decisão e Random Forest. Novamente, o **Random Forest** foi superior, apresentando o menor Erro Absoluto Médio (MAE de 66.71 W/m²) e conseguindo explicar cerca de 84,5% da variância (R² de 0.84). A análise confirmou o forte peso da variável "hora" (devido ao ciclo diário de radiação solar), mas ressalvou-se que estimar radiação (W/m²) não traduz de forma direta a energia elétrica gerada em kWh.
