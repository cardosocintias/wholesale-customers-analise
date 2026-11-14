# Análise de clientes grossistas

Projeto académico de análise do conjunto **Wholesale Customers**, com exploração e preparação dos dados, classificação do canal de distribuição e segmentação de clientes com K-Means.

## Conteúdo

- `Projeto.ipynb` — notebook com análise, visualizações e conclusões.
- `input/Dataset_F_Wholesale.csv` — dados usados pelo notebook.
- `output/` — pasta onde o notebook grava o ficheiro final tratado.

## Como executar

1. Instale Python 3.10 ou superior.
2. Crie e ative um ambiente virtual (opcional, mas recomendado).
3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Abra o notebook com Jupyter:

   ```bash
   jupyter notebook Projeto.ipynb
   ```

Execute as células pela ordem apresentada, a partir da pasta principal do projeto. O notebook lê `input/Dataset_F_Wholesale.csv` e grava o resultado tratado em `output/Dataset_F_Wholesale_Final.csv`.

## O que foi feito

- Análise exploratória de 444 registos e 8 atributos.
- Preenchimento dos valores em falta em `Milk`, `Grocery` e `Delicassen` com medianas calculadas por canal.
- Remoção de 4 registos duplicados, ficando 440 observações.
- Análise de valores extremos pelo método da amplitude interquartil; os registos foram mantidos por poderem representar clientes reais.
- Classificação de `Channel` com árvore de decisão.
- Segmentação em 6 grupos com K-Means e análise dos respetivos perfis.

## Limitações conhecidas

A preparação dos dados para a classificação é feita antes da divisão treino/teste e usa `Channel` no preenchimento de valores em falta. Isto pode introduzir fuga de informação e tornar as métricas otimistas. No K-Means, as variáveis são usadas sem normalização e `Region` é codificada numericamente, o que atribui distâncias artificiais às categorias. Estas escolhas são discutidas no notebook e devem ser consideradas ao interpretar os resultados.

## Tecnologias

Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn e Jupyter.
