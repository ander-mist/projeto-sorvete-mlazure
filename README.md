# 🍦 Prevendo Vendas de Sorvete com Machine Learning | Azure + MLflow

Este projeto demonstra como construir um modelo preditivo que estima as vendas de sorvete com base na temperatura do dia, usando Azure Machine Learning, MLflow e também Azure AutoML.

---

## ⚙️ Tecnologias Utilizadas

- Python
- Pandas / Scikit-learn
- Azure Machine Learning
- MLflow
- Automated ML (AutoML)
- Jupyter Notebooks

---

## 💾 Dataset

- Dataset com 100 registros sintéticos:
- Colunas: `Data`, `Temperatura`, `Sorvetes_Vendidos`.

| Data       | Temperatura | Sorvetes_Vendidos |
|------------|-------------|--------------------|
| 2024-01-01 | 20.3        | 47                 |
| 2024-01-02 | 24.6        | 60                 |
| 2024-01-03 | 30.1        | 90                 |

---

## 🚀 Passo a Passo do Projeto

### 🔹 1️⃣ Preparação do Ambiente

1. Criar **Azure Machine Learning Workspace**.
2. Criar uma `Compute Instance`.
3. Subir o arquivo `dataset_sorvetes_100_registros.csv` para o Azure.

---

### 🔹 2️⃣ Treinamento com MLflow

- Conexão do workspace no Python.
- Treinamento com `LinearRegression`.
- Registro do modelo no Azure via MLflow.

---

## 🤖 Automated ML (AutoML) — Passo a Passo

Além do treinamento manual, o mesmo dataset foi utilizado no **Azure AutoML** para comparar diferentes algoritmos.

### 💡 Como configurar o AutoML:

1️⃣ Acesse o portal do Azure:  
👉 https://ml.azure.com

2️⃣ No menu lateral, clique em:  
**Automated ML** → `+ New Automated ML run`.

![Passo 1 - Novo AutoML](https://workspaceproje8557981900.blob.core.windows.net/imagens-sorvete/novoJob.png)

---

3️⃣ Escolha o dataset `dataset_sorvetes_100_registros.csv` e clique em **Next**.

![Passo 2 - Selecionar Dataset](https://workspaceproje8557981900.blob.core.windows.net/imagens-sorvete/dataSet.png)

---

4️⃣ Configure o experimento:
- Experimento: `sorvete-projeto-novo-data`
- Compute: `Compute Cluster`.
- Task type: `Regression`.
- Target column: `Sorvetes_Vendidos`.

![Passo 3 - Configuração do Job](https://workspaceproje8557981900.blob.core.windows.net/imagens-sorvete/trainingJob.png)

---

5️⃣ Após iniciar, o AutoML irá testar o modelo:  
- XGBoost

💡 Tela de execução:  
![Passo 4 - Modelos em Execução](https://workspaceproje8557981900.blob.core.windows.net/imagens-sorvete/autoMLOverwied.png)

---

6️⃣ Quando finalizado, o AutoML exibe o **melhor modelo encontrado**.

Exemplo de resultados:  
- Métrica principal: `R² Score`.
- Opção de deploy direto via botão `Deploy`.

![Passo 5 - Melhor Modelo Escolhido](https://workspaceproje8557981900.blob.core.windows.net/imagens-sorvete/melhorModelo.png)

---

## 💡 Insights

- O AutoML encontrou modelos que superaram o `LinearRegression` em alguns testes.
- A combinação de MLflow + AutoML facilita versionamento e produtividade.
- Próximo passo: adicionar novas variáveis como "Dia da Semana", "Chuva", "Eventos".

---

## 🔥 Conclusão

Esse projeto mostrou como:
- Construir e treinar um modelo manualmente com MLflow.
- Automatizar a busca por modelos com AutoML.
- Implantar modelos no Azure com apenas alguns cliques.
