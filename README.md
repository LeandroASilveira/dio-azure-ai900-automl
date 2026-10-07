# 🚲 Previsão de Aluguel de Bicicletas com Azure Machine Learning (AutoML)

Projeto prático desenvolvido para o módulo de Inteligência Artificial da **DIO (Digital Innovation One)**, aplicando os conceitos de Machine Learning Automatizado do exame Microsoft Azure AI-900.

## 📊 Racional do Projeto e Processo

1. **Importação dos Dados:** 
   O conjunto de dados `bike-rentals.csv` foi baixado e importado manualmente para o Azure Machine Learning Studio como um Ativo de Dados Tabular devido a instabilidades na importação via URL web.

2. **Configuração do AutoML (Trabalho de Regressão):**
   - **Tipo de Tarefa:** Regressão (previsão de valores numéricos contínuos).
   - **Coluna de Destino:** `rentals` (quantidade de aluguéis de bicicletas).
   - **Métrica Primária:** Normalized Root Mean Squared Error (NRMSE).
   - **Modelos Treinados:** O Azure testou algoritmos como *Random Forest* e *LightGBM*, gerando um modelo consolidado via *VotingEnsemble*.

3. **Métricas de Sucesso:**
   O modelo alcançou uma excelente performance com um **R2 Score (Coeficiente de Determinação) próximo a 0.70**, demonstrando forte capacidade de explicar a variação na demanda de bicicletas com base em variáveis climáticas e temporais.

4. **Desafio de Infraestrutura (Deployment):**
   Durante a fase de criação do ponto de extremidade em tempo real, foram enfrentados limites rígidos de cota de vCPUs da assinatura acadêmica/teste do Azure (bloqueando famílias de VMs maiores) e falha de inicialização por falta de memória na instância `Standard_DS1_v2`. Como solução de engenharia, o design do pipeline e as configurações estruturais do JSON foram validados e documentados no arquivo `endpoints.json`.

## 🛠️ Tecnologias Utilizadas

- **Microsoft Azure Machine Learning Studio**
- **Azure AutoML Studio (Regression Engine)**
- **Git & GitHub**
