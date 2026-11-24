# T1 - Aprendizado Não Supervisionado (Dataset Regenera)

Aprendizado de Máquina - Prof. Me. Otávio Parraga - PUCRS

## Integrantes

| Nome | 
|---|
|Thomaz Szeckir| 
|Dhara Hadi| 
|Matheus Azevedo| 
|Gabriel Ottonelli| 
|Samuel Morales|
|Júlia Bettiol|

## Algoritmos escolhidos

| Tarefa | Algoritmo 1 | Algoritmo 2 |
|---|---|---|
| A - Agrupamento | K-Means | Hierárquico aglomerativo com ligação de Ward |
| B - Redução de dimensionalidade | PCA (linear) | UMAP (não linear) |

## Estrutura dos arquivos

| Arquivo | Conteúdo |
|---|---|
| `T1_Regenera.ipynb` | notebook com todo o trabalho, já executado (código, figuras e interpretações) |
| `Data_REG.tsv` | dataset original |
| `README.md` | este arquivo |

## Como reproduzir

É preciso ter Python 3.9 ou mais recente, e o `Data_REG.tsv` precisa estar na mesma pasta do notebook.

```bash
python -m venv .venv
source .venv/bin/activate          # no Windows: .venv\Scripts\activate
pip install pandas numpy scikit-learn scipy matplotlib seaborn umap-learn jupyter
jupyter notebook T1_Regenera.ipynb
```

Depois é só abrir o notebook e rodar Kernel > Restart & Run All. Pelo terminal também dá:

```bash
jupyter nbconvert --to notebook --execute --inplace T1_Regenera.ipynb
```

### Semente

Tudo que é aleatório usa `SEED = 42` (K-Means, PCA, UMAP, validação cruzada e as subamostras do teste de estabilidade). O Ward é determinístico. Nos testes de estabilidade da UMAP usamos as sementes 0 e 1 de propósito. Com a mesma versão das bibliotecas os resultados se repetem, mas em outra versão do `umap-learn` ou do `numba` a figura da UMAP pode sair rotacionada ou espelhada, mantendo a mesma estrutura.

### Versões usadas

| Biblioteca | Versão |
|---|---|
| Python | 3.9.6 |
| pandas | 2.3.3 |
| numpy | 2.0.2 |
| scikit-learn | 1.6.1 |
| scipy | 1.13.1 |
| matplotlib | 3.9.4 |
| seaborn | 0.13.2 |
| umap-learn | 0.5.12 |
| numba | 0.60.0 |

## Delimitação do desenvolvimento

| Veio de biblioteca | Implementado pelo grupo |
|---|---|
| K-Means, AgglomerativeClustering, PCA, StandardScaler, RobustScaler, KNN e validação cruzada (scikit-learn) | limpeza dos dados com o log de correções |
| silhueta, Davies-Bouldin, ARI, NMI e trustworthiness (scikit-learn) | codificação multi-hot da morfologia |
| `linkage`, `dendrogram` e `chi2_contingency` (SciPy) | função `preprocess` com as decisões parametrizadas |
| UMAP (umap-learn) | teste de estabilidade por subamostras de 80% |
| | cálculo do erro de reconstrução MSE(d) |
| | comparação entre as partições do K-Means e do Ward |
| | análise de sensibilidade ao pré-processamento |
| | todas as figuras e interpretações |
