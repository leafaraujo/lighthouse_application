# lighthouse_application

A versão do Python utilizada localmente foi a 3.8.10, e as bibliotecas estão listadas no arquivo de requisitos.

## Instruções para rodar o projeto

Para conseguir rodar a EDA, e o projeto para a criação do modelo basta que abra uam guia do Jupyter Notebook com todos os requisitos instalados e configurados e selecione a opção de rodar todas as células.

## Instruções para importar o modelo

Para carregar o modelo em seu projeto, deve executar os seguintes comandos:

```
import pickle

with open('modelo.pkl', 'rb') as file:
    rental_model = pickle.load(file)
```

Depois disso, você pode criar um dataframe apenas com os dados que deseja utilizar para prever o preço com algumas alterações, levando como exemplo o que foi proposto dentro do relatório, no meu código ele ficou assim:

```
pessoa_df = pd.DataFrame([{
     'host_id': 2845,
     'latitude': 40.75362,
     'longitude': -73.98377,
     'minimo_noites': 1,
     'disponibilidade_365': 355,
    'Entire home/apt': 1,
    'Private room': 0,
    'Shared room': 0
}])
```

Foram retiradas algumas variáveis que não eram importantes para o modelo, e também adicionando as tabelas dummies do tipo de imóvel, bastando apenas que preencha com 0 (False), os imóveis que não são o que deseja severificar e 1 (True) o tipo de imóvel que é o que deseja ser verificado.
