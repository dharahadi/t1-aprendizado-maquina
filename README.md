# T1 - Aprendizado Não Supervisionado (Dataset Regenera)
 
Aprendizado de Máquina - Prof. Me. Otávio Parraga - PUCRS
 
## Integrantes
 
| Nome | Matrícula |
|---|---|
| Júlia Bettiol de Oliveira | 23102448 |
| Samuel da Silva Morales | 23108180 |
| Thomaz Gomes Szeckir | 23102712 |
| Dhara Husein Abdel Hadi | 23102242 |
| Matheus Jefremovas Azevedo | 23180103 |
| Gabriel Schwengber Ottonelli | 23107019 |
 
## Algoritmos escolhidos
 
| Tarefa | Algoritmo 1 | Algoritmo 2 |
|---|---|---|
| A - Agrupamento | K-Means | Hierárquico aglomerativo com ligação de Ward |
| B - Redução de dimensionalidade | PCA (linear) | UMAP (não linear) |
 
## Arquivos
 
| Arquivo | Conteúdo |
|---|---|
| `T1_Regenera.ipynb` | notebook com todo o trabalho, já executado |
| `Data_REG.tsv` | dataset original |
| `README.md` | este arquivo |
 
## Como rodar
 
Requisito: Python 3.9 a 3.12.
 
1. Baixe o projeto:
```bash
git clone https://github.com/dharahadi/t1-aprendizado-maquina.git
cd t1-aprendizado-maquina
```
 
2. Crie o ambiente virtual:
```bash
python3 -m venv .venv          # no Windows: python -m venv .venv
```
 
3. Ative o ambiente:
```bash
source .venv/bin/activate      # macOS e Linux
.venv\Scripts\activate         # Windows
```
 
4. Instale as dependências:
```bash
pip install pandas==2.3.3 numpy==2.0.2 scikit-learn==1.6.1 scipy==1.13.1 matplotlib==3.9.4 seaborn==0.13.2 umap-learn==0.5.12 numba==0.60.0 jupyter
```
 
5. Abra o notebook:
```bash
jupyter notebook T1_Regenera.ipynb
```
 
6. No Jupyter, clique em **Kernel > Restart Kernel and Run All Cells**.
## Sementes
 
Todas as sementes já estão fixadas no código:
 
- `SEED = 42` no K-Means, PCA, UMAP, subamostras do teste de estabilidade e validação cruzada.
- Sementes `0` e `1` só no teste de estabilidade da UMAP.
## Delimitação do desenvolvimento
 
| Veio de biblioteca | Implementado pelo grupo |
|---|---|
| K-Means, AgglomerativeClustering, PCA, StandardScaler, RobustScaler, KNN e validação cruzada (scikit-learn) | limpeza dos dados com o log de correções |
| silhueta, Davies-Bouldin, ARI, NMI e trustworthiness (scikit-learn) | codificação multi-hot da morfologia |
| `linkage`, `dendrogram`, `fcluster`, `cophenet`, `pdist` e `chi2_contingency` (SciPy) | função `preprocess` com as decisões parametrizadas |
| UMAP (umap-learn) | V de Cramér, inércia do Ward e teste de estabilidade |
| | erro de reconstrução MSE(d), comparação K-Means × Ward e análise de sensibilidade |
| | todas as figuras e interpretações |