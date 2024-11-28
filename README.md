### Documentação do Projeto

---

# **Notebook de Treinamento e Previsão de Séries Temporais**

Este repositório contém dois notebooks principais para trabalhar com previsões de séries temporais usando Redes Neurais LSTM:

1. **Notebook de Treinamento** (`Machine Learning Engineering  - LSTM AAPL Prediction Model.ipynb`): 
   - Utiliza dados históricos para treinar um modelo LSTM que prevê preços futuros.
   - Salva o modelo treinado para reutilização futura.

2. **Notebook de Previsão**:
   - O modelo previamente treinado é carregado.
   - Permite realizar previsões diretamente no Google Colab usando novos dados históricos.

---

## **Notebook 1: Treinamento do Modelo (`Machine Learning Engineering  - LSTM AAPL Prediction Model.ipynb`)**

### **Descrição**
O notebook utiliza dados financeiros históricos obtidos da api do Yahoo Finance para treinar um modelo LSTM com o objetivo de prever valores de fechamento futuros. As principais etapas incluem:
1. **Aquisição de Dados**: Coleta de dados financeiros da API do Yahoo Finance.
2. **Pré-Processamento**: Normalização dos dados com `StandardScaler` e criação de janelas temporais.
3. **Treinamento**: Uso do modelo LSTM com validação cruzada (`GridSearchCV`).
4. **Avaliação**: Métricas de desempenho como MAE, MSE, RMSE e MAPE. Além disso possui inúmeros gráficos para visualizar a generalização do modelo.
5. **Salvamento do Modelo**: Exportação do modelo treinado para o Google Drive.

---

### **Como Usar**
1. **Pré-requisitos:**
   - Certifique-se de ter acesso ao Google Drive para salvar o modelo treinado.

2. **Passo a Passo no Notebook:**
   - Faça o upload do arquivo `Machine Learning Engineering  - LSTM AAPL Prediction Model.ipynb` no Google Colab.
   - Execute as células sequencialmente para:
     - Carregar e processar os dados históricos.
     - Treinar o modelo LSTM com os melhores hiperparâmetros.
     - Avaliar o modelo.
     - Salvar o modelo treinado no Google Drive.

---


### **Resultados do Treinamento**
O modelo é avaliado usando as métricas abaixo:
- **MAE (Erro Médio Absoluto)**: 4.94
- **MSE (Erro Quadrático Médio)**: 37.75
- **RMSE (Raiz do Erro Quadrático Médio)**: 6.14
- **MAPE (Erro Percentual Absoluto Médio)**: 2.22%

Esses resultados indicam a capacidade do modelo de prever com precisão os valores futuros dentro de uma margem aceitável de erro, com baixo desvio percentual em relação aos valores reais. Além disso, gráficos comparativos e análise de resíduos são gerados para avaliar a qualidade do modelo.

---

### **Arquivos Gerados**
- **Modelo Treinado**: Salvo em `/content/drive/My Drive/best_lstm_model_v4.keras`.
- **Gráficos**: Exibidos no final do notebook, incluindo:
  - Comparação de previsões e valores reais.
  - Distribuição dos resíduos.

---

## **Notebook 2: Previsões Diretamente com Google Colab**

### **Descrição**
Este notebook permite carregar o modelo previamente treinado e realizar previsões baseadas em novos dados históricos. Ele é ideal para quem deseja realizar previsões rápidas sem re-treinar o modelo, ou consumir/construir uma API.

---

### **Como Usar**
1. **Pré-requisitos:**
   - Certifique-se de ter o arquivo do modelo treinado (`best_lstm_model_v4.keras`) salvo no Google Drive.
   - Dependências necessárias:
     ```bash
     pip install tensorflow keras yfinance matplotlib seaborn
     ```

2. **Passo a Passo:**
   - Faça o upload do notebook no Google Colab.
   - Monte seu Google Drive no Colab:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```
   - Carregue o modelo salvo:
     ```python
     model = tf.keras.models.load_model('/content/drive/My Drive/best_lstm_model_v4.keras')
     ```
   - Execute o notebook para obter previsões de preços futuros.

---

### **Saída**
- Previsões para os próximos dias.
  - Exemplo:
    ```json
    [
      {
        "date": "2024-11-23",
        "predicted_value": 230.45
      }
    ]
    ```

---

## **Estrutura do Repositório**

```
.
├── Machine Learning Engineering  - LSTM AAPL Prediction Model.ipynb       # Notebook de treinamento do modelo LSTM
├── Machine Learning Engineering - LSTM - Previsões com modelo.ipynb       # Notebook para realizar previsões
├── best_lstm_model_v4.keras                                               # Modelo de Deep Learning LSTM
├── README.md                                                              # Documentação do projeto
└── requirements.txt                                                       # Lista de dependências do projeto
```

---

## **Como Contribuir**
- Sugestões e melhorias são bem-vindas.
- Para contribuir, faça um fork do repositório, implemente suas alterações e abra um Pull Request.

---

## **Contato**
- **Autor:** Rodrigo Siliunas
- **E-mail:** rodrigo.siliunas12@gmail.com
- **GitHub:** [github.com/RodrigoSiliunas](https://github.com/RodrigoSiliunas)
- **LinkedIn:** [linkedin.com/in/rodrigo-siliunas](https://linkedin.com/in/rodrigo-siliunas)

---