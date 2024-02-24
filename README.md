# Desafio de Ciência de Dados Indicium
## Participante: Guilherme Coelho Minervino

## Ferramentas utilizadas para o projeto:
- PyCharm with Jupyter Notebook
- Miniconda
- Python 3.12.1
- Windows 11
- Todos os pacotes instalados estão contidos em `requirements.txt`

## Visão geral do projeto
- Diagrama:
![Diagram](https://github.com/guico3lho/indicium_desafio/blob/main/assets/pipeline_diagram.png?raw=true)
- `assets` contém o diagrama da pipe line e o melhor modelo treinado
- `pipeline` contém o fluxo de arquivos que compõe a pipeline, composto por
  - (1) `eda.ipynb`: Análise exploratória, resposta das perguntas do desafio, conclusão e decisões para os modelos preditivos
  - (2) `evaluate_models_train_split.ipynb`: avaliação de três modelos lineares diferentes utilizando validação cruzada no split de treino
  - (3) `apply_model_split.ipynb: aplicação` do melhor modelo no split de teste

## Como instalar e executar
- Instalar Anaconda ou Miniconda
- Criar um ambiente de desenvolvimento com Python 3.12.1
- Instalar os pacotes do `requirements.txt` executando `pip install -r requirements.txt`
- Importar o dataset no projeto (no meu caso, usei a biblioteca `gdown`, mas qualquer outra forma pode ser utilizada)
- Caso decida pelo `gdown`, basta executar o notebook normalmente, que irá baixar o dataset de um repositório do drive que deixei público
- Tudo pronto

## Conclusão do desafio
- A análise exploratória trouxe muitos insights interessantes, descritos no notebook `eda.ipynb`. Esses insights foram importantes para encontrar as características que mais influenciam 
o preço de locação de um apartamento em Nova York
- Inicialmente, tentou-se utilizar apenas as 4 variaveis com maior correlação com o preço para os modelos preditivos. Mas os resultados não foram satisfatórios, com RMSE em torno de 38.83.
- Ao utilizar todas as variáveis, o RMSE ficou um pouco melhor, em torno de 36. Mas ainda sim muito alto. Valores bons de RMSE costumam ser abaixo de 10.
- Todos os três modelos lineares testados em splits de treino tiveram desempenho relativamente igual. Portanto, foi escolhido um modelo arbitrário dos três
- O modelo Ridge() obteve um RMSE enorme de 1255 no split de teste. E o gráfico comparando o valor predito e o valor real do apartamento pode ser visualizado em `apply_model_test_split`
- O único resultado que achei promissor foi ao prever o preço da amostra do desafio. O valor predito foi de 167, relativamente perto de 225 (valor real)