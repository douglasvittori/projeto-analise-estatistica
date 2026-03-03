# 📈 Análise Preditiva de Lucro Líquido para Motoristas de Aplicativo

Este projeto utiliza Regressão Linear Múltipla (OLS) para identificar e quantificar os fatores que mais impactam o lucro líquido real de uma operação de transporte por aplicativo.

---

## 🎯 Objetivo do Projeto

O intuito é transformar dados brutos de rodagem e faturamento em insights acionáveis, respondendo a perguntas como: "Quanto cada real a mais no combustível come do meu lucro?" ou "Qual a eficiência real do aumento de faturamento?"

---

## 🛠️ Tratamento de Dados e Engenharia de Atributos

A preparação dos dados foi uma etapa crítica para garantir a aderência às suposições estatísticas. O fluxo de trabalho incluiu:

* **Limpeza e Outliers:** Identificação e tratamento de valores discrepantes que poderiam desviar a reta de regressão.
* **Transformação Logarítmica:** Aplicação de log na variável dependente (Lucro Líquido) para estabilizar a variância e aproximar a distribuição da normalidade.
* **Feature Selection:** Filtragem de variáveis irrelevantes (como datas e feriados sem significância) através da análise de P-valores, mantendo apenas preditores robustos.
* **Tratamento de Multicolinearidade:** Utilização do VIF (Variance Inflation Factor) para eliminar variáveis redundantes, garantindo que cada coeficiente represente um impacto independente.
* **Esconamento:** Padronização das variáveis para que a diferença de magnitude entre quilometragem e faturamento não enviesasse o aprendizado do modelo.

---

## 🛠️ Tecnologias Utilizadas
* Python 3.10+
* Pandas & Numpy: Manipulação e limpeza de dados.
* Statsmodels: Modelagem estatística e testes de hipóteses.
* Seaborn & Matplotlib: Visualização de resíduos e correlações.

---

## 📊 O Modelo Final

Após um rigoroso processo de seleção de variáveis (Feature Selection) e limpeza de multicolinearidade (VIF), o modelo final focou em três pilares fundamentais:

* Km Rodados (x1​)
* Preço do Combustível (x2​)
* Faturamento Total (x3​)

Performance e Validação

O modelo foi validado sob as 5 suposições:

* ✅ Linearidade: Teste Rainbow com p-valor de 0.93.
* ✅ Independência: Durbin-Watson de 2.015 (ausência de autocorrelação).
* ✅ Normalidade: Teste Jarque-Bera confirmando distribuição normal dos erros.
* ✅ Multicolinearidade: Todas as variáveis com VIF < 3.
* ✅ R² Ajustado: ~0.50 (Explicando 50% da variância do lucro em um cenário de alta volatilidade).

---

## 💡 Insights Principais

* Sensibilidade ao Combustível: Cada aumento de R$ 1,00 no combustível impacta negativamente o lucro em 7,17%.
* Escalabilidade: O aumento de faturamento bruto converte cerca de 10,16% em lucro líquido direto, após descontados os custos fixos e variáveis.

--- 

## 📂 Como Executar

* Clone o repositório.
* Instale as dependências: pip install -r requirements.txt.
* Execute o notebook analise_lucro.ipynb.
