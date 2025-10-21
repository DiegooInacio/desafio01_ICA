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

```bash``
pip install numpy scikit-learn torch matplotlib pandas seaborn

## 🚀 Como Executar

O código é projetado para ser executado em um ambiente de notebook (Google Colab ou Jupyter), pois utiliza comandos shell (`!wget`) para baixar as bases de dados e blocos de código sequenciais.

1.  **Copie** todo o código para uma célula do seu notebook.
2.  **Execute** a célula.

O script fará o download dos dados, treinará a MLP em cada base, calculará todas as métricas ($M$, $\sigma M$, $T^\star$) e exibirá o ranqueamento final em formato de tabela e gráficos comparativos.

## 📊 Metodologia de Avaliação e Score (S)

O ranqueamento é determinado pelo **Score Final (S)**, que equilibra a qualidade preditiva e a eficiência.

### Fórmula do Score Final (S)

O modelo com o maior $S$ é o vencedor:

$$S = 0.70 \cdot M - 0.20 \cdot \sigma M + 0.10 \cdot T^\star$$

| Componente | Peso | Objetivo | Descrição |
| :--- | :--- | :--- | :--- |
| **Média Agregada ($M$)** | **0.70** | Máximo | Média das 4 métricas (Acc, Prec, Rec, F1) do K-Fold. **Qualidade Preditiva.** |
| **Desvio Agregado ($\sigma M$)** | **0.20** | Mínimo | Média do desvio padrão das 4 métricas. **Estabilidade/Robustez.** |
| **Tempo Normalizado ($T^\star$)** | **0.10** | Máximo | Tempo de inferência normalizado e invertido. **Eficiência/Latência.** |
