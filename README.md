# Análise de Preços de Aluguéis em São Paulo — Desafio SYNAPTA (Opção 1)

Este repositório apresenta a exploração, limpeza e análise estatística de um conjunto de dados de imóveis para aluguel na cidade de São Paulo, desenvolvido como solução para o desafio da **SYNAPTA**.

---

## 📋 Visão Geral e Carga dos Dados
* **Dataset Inicial:** 11.657 linhas e 8 colunas (`address`, `district`, `area`, `bedrooms`, `garage`, `type`, `rent`, `total`).
* **Tipos de Dados:** 5 colunas numéricas (`int64`) e 3 colunas de texto (`str`).

---

## 🧹 Limpeza e Tratamento de Dados
* **Valores Nulos e Duplicados:** A checagem inicial confirmou que o arquivo original não possuía valores ausentes nem registros duplicados.
* **Correção de Inconsistências:** Através da inspeção com o `.describe()`, identificou-se valores mínimos iguais a `0.0` nas colunas `area` e `rent`. Como um imóvel real não pode apresentar área ou aluguel zerados, aplicou-se um filtro para reter apenas valores estritamente maiores que zero.
* **Resultado Final:** Apenas 2 registros inconsistentes foram descartados, resultando em um DataFrame limpo com **11.655 linhas**.

---

## 📊 Estatísticas de Preços (Aluguel)
* **Preço Médio:** R$ 3.250,96
* **Preço Mediano:** R$ 2.415,00
* **Insight Estatístico:** A **média** é puxada para cima devido a imóveis de alto padrão (como mansões e coberturas de luxo), enquanto a **mediana** representa com muito mais precisão e realism o custo típico pago pela maioria dos inquilinos.

---

## 🗺️ Análise Geográfica por Bairros (`district`)
* **Critério de Amostragem:** Para evitar vieses causados por amostras reduzidas, o ranking de bairros filtrou apenas localidades com **pelo menos 30 anúncios** publicados.

### 🌟 Top 5 Bairros com Maiores Preços Médios
1. **Jardim Leonor** — R$ 7.455,74
2. **Tamboré** — R$ 6.912,68
3. **Cerqueira César** — R$ 6.750,66
4. **Jardim Paulista** — R$ 6.305,96
5. **Paraíso** — R$ 6.285,56

### 🏷️ Top 5 Bairros com Menores Preços Médios
1. **Taboão** — R$ 1.473,14
2. **Sé** — R$ 1.593,30
3. **Campos Elíseos** — R$ 1.646,79
4. **Santa Efigênia** — R$ 1.647,53
5. **Vila Ema** — R$ 1.736,86

---

## 📈 Visualizações Gráficas
O projeto gera as seguintes visualizações principais para suporte à tomada de decisão:
1. **Histograma:** Exibe a distribuição de frequência dos valores de aluguel.
2. **Gráfico de Dispersão (Scatter Plot):** Relaciona de forma direta a área útil (em $m^2$) com o valor do aluguel (`rent`).
3. **Gráfico de Barras:** Apresenta o ranking visual dos bairros mais caros da capital.
