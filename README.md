# DESAFIO 1 - ICA

Este projeto implementa um *framework* de avaliação de modelos de Machine Learning (MLP) utilizando o **K-Fold Cross-Validation**, cálculo de **métricas de desempenho agregadas** e **medição de tempo de inferência**. O objetivo é ranquear o desempenho do modelo em três bases de dados bidimensionais (`Two Moons`, `Banana`, `Ripley`) usando um **Score Final (S)** baseado em qualidade e eficiência.

## 📄 Estrutura do Código

O projeto é contido em um único script/notebook (como Colab ou Jupyter) que:

1. Baixa automaticamente as bases de dados.
2. Define a arquitetura da MLP (2 $\rightarrow$ 8 $\rightarrow$ 1).
3. Executa a avaliação em K-Fold e a medição de tempo em repetições.
4. Calcula o Score Final (S) e apresenta os resultados em tabelas e gráficos de barras.

## 🛠️ Dependências

Este código requer as seguintes bibliotecas Python. Elas podem ser instaladas via `pip`:

```bash
pip install numpy scikit-learn torch matplotlib pandas seaborn
