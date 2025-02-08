# Projeto de Previsão de Preços

Este é um projeto de previsão de preços de imóveis usando modelos de machine learning. O projeto utiliza bibliotecas como `scikit-learn`, `pandas`, e `numpy` para realizar análises, treinar modelos e realizar previsões.

## Requisitos do Sistema

- Python 3.8 ou superior
- Pip instalado
- Sistema operacional compatível (Windows, macOS ou Linux)

## Instalação

1. Clone o repositório do projeto:

   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   cd seu-repositorio
   ```

2. Crie um ambiente virtual (opcional, mas recomendado):

   ```bash
   python -m venv venv
   source venv/bin/activate  # No Windows: venv\Scripts\activate
   ```

3. Instale as dependências do projeto:

   ```bash
   pip install -r requirements.txt
   ```

## Uso

### Passo 1: Preparar o Dataset

Certifique-se de que os dados de entrada estejam em um arquivo CSV no formato esperado. O projeto requer que o dataset tenha colunas como `bairro_group`, `bairro`, `latitude`, `longitude`, entre outras.

### Passo 2: Executar a Análise Exploratória

O notebook `EDA.ipynb` contém a análise exploratória dos dados. Para executá-lo:

1. Abra o Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

2. Navegue até o arquivo `EDA.ipynb` e execute todas as células.

### Passo 3: Realizar Previsão para Novos Dados

Para prever o preço de novos imóveis:

1. Formate os dados de entrada como um DataFrame, garantindo que as colunas sejam consistentes com o conjunto de treinamento.
2. Carregue o modelo salvo (ex.: `ensemble_model.pkl`) e faça as previsões:

   ```python
   import pickle
   import pandas as pd

   # Carregar o modelo treinado
   with open('ensemble_model.pkl', 'rb') as file:
       model = pickle.load(file)

   # Dados de exemplo
   novo_dado = pd.DataFrame({
       'bairro_group': ['Manhattan'],
       'bairro': ['Midtown'],
       'latitude': [40.75362],
       'longitude': [-73.98377],
       # Adicione outras colunas conforme necessário
   })

   # Fazer previsão
   previsao = model.predict(novo_dado)
   print(previsao)
   ```



