# Capacitismo Linguístico em Português Brasileiro

### Uma Análise Estatística do Capta-PTBR — Estágio 2

Este repositório apresenta as análises estatísticas desenvolvidas no contexto da pesquisa **Capacitismo Linguístico no Português Brasileiro: Uma Análise Computacional da Representação de Pessoas com Deficiência**, vinculada à Universidade Federal de Mato Grosso do Sul (UFMS).

O estudo investiga a identificação do capacitismo linguístico em sentenças do português brasileiro, considerando características lexicais, classificações humanas e divergências interpretativas.

As análises utilizam métodos estatísticos descritivos e inferenciais aplicados ao **Capta-PTBR — Estágio 2**, composto por 1.500 sentenças avaliadas por 13 anotadores.

---

## 1. Objetivos

O objetivo principal é investigar fatores associados à classificação do capacitismo linguístico e avaliar a consistência das anotações humanas.

**Objetivos específicos:**

- Investigar associações entre características lexicais e a classificação de capacitismo.
- Avaliar a concordância entre anotadores.
- Identificar fatores associados às divergências nas avaliações.
- Analisar a estabilidade das decisões majoritárias.
- Examinar a robustez das estimativas estatísticas.

## 2. Corpus Capta-PTBR

O Capta-PTBR foi desenvolvido para apoiar a investigação computacional do capacitismo linguístico no português brasileiro.

### Estágio 1 — Recuperação de sentenças

- Aplicação de técnicas de Processamento de Linguagem Natural (PLN).
- Utilização de padrões léxico-sintáticos no corpus TuPy-E.
- Identificação de sentenças potencialmente capacitistas.
- Recuperação de 741 sentenças para análise.

### Estágio 2 — Anotação humana

- Seleção de 1.500 sentenças.
- Participação de 13 anotadores.
- Avaliação em três dimensões:

| Dimensão | Classes |
|---|---|
| Capacitismo | Sim / Não |
| Categoria | Insulto direto / Metafórico / Aparentemente neutro |
| Polaridade | Positiva / Negativa / Neutra |

As classificações foram consolidadas por voto majoritário.

**Distribuição das classificações:**

| Classificação | Sentenças | Percentual |
|---|---:|---:|
| Capacitistas | 588 | 39,2% |
| Não capacitistas | 912 | 60,8% |
| Total | 1.500 | 100% |

## 3. Metodologia Estatística

As análises foram organizadas em quatro eixos.

### 3.1 Análise descritiva

Foram examinados:

- Frequências e proporções das classificações.
- Presença de termos do dicionário lexical.
- Distribuição das avaliações individuais.
- Proporções de concordância, consenso forte e unanimidade.

**Finalidade:** caracterizar as sentenças e compreender a distribuição das classificações.

### 3.2 Testes de associação e regressão logística

Métodos utilizados:

- Teste qui-quadrado de independência.
- Teste de Mann–Whitney.
- Regressão logística binária.

Foram ajustados dois modelos:

**M1 — Classificação de capacitismo**

Investiga a associação entre presença lexical e classificação majoritária de capacitismo.

**M2 — Discordância entre anotadores**

Investiga a associação da presença lexical e da classificação majoritária com a ocorrência de discordância.

### 3.3 Concordância entre anotadores

Foram utilizados:

- Kappa de Fleiss.
- Kappa de Cohen.
- Teste Q de Cochran.
- Teste de McNemar.
- Correção de Holm para comparações múltiplas.

**Finalidade:** avaliar a concordância global e entre pares de anotadores, além de investigar diferenças nas tendências individuais de classificação.

### 3.4 Análises de robustez

Foram empregados:

- Bootstrap com 10.000 replicações.
- Intervalos de confiança de 95%.
- Diferentes limiares de consenso.
- Análise *leave-one-rater-out*.

**Finalidade:** avaliar a precisão das estimativas e a estabilidade das decisões majoritárias diante da retirada individual de anotadores.

## 4. Principais Resultados

### 4.1 Associação entre presença lexical e capacitismo

A presença de termos do dicionário apresentou forte associação com a classificação de capacitismo.

| Indicador | Resultado |
|---|---|
| Qui-quadrado | χ²(1) = 1086,92 |
| Valor-p | p < 0,001 |
| V de Cramér | 0,8512 |

Entre as sentenças que continham termos do dicionário, 87,84% foram classificadas como capacitistas (556 de 633).

Entre as sentenças sem esses termos, 3,69% receberam classificação capacitista (32 de 867).

Esses resultados indicam que a presença lexical está fortemente associada à classificação, mas não é suficiente para determinar a ocorrência de capacitismo.

### 4.2 Concordância entre anotadores

| Dimensão | Kappa de Fleiss |
|---|---:|
| Classificação binária | 0,6405 |
| Categoria | 0,1719 |
| Polaridade | 0,2154 |

A concordância foi maior na classificação binária, enquanto categoria e polaridade apresentaram divergências mais expressivas.

O teste Q de Cochran identificou diferenças estatisticamente significativas nas tendências individuais dos anotadores (p < 0,001).

### 4.3 Regressão logística

| Métrica | M1 | M2 |
|---|---:|---:|
| AUROC | 0,9306 | 0,5801 |
| Odds Ratio — presença lexical | 188,42 | 2,56 |
| Pseudo-R² de McFadden | 0,6303 | 0,0190 |

**M1:** apresentou forte associação entre presença lexical e classificação de capacitismo.

**M2:** indicou associação entre presença lexical e discordância, mas apresentou baixa capacidade explicativa e discriminativa.

**Nota metodológica:** não foi aplicada validação cruzada k-fold. Os modelos foram utilizados principalmente para investigação de associações estatísticas. Os valores de AUROC foram calculados nos dados analisados e não representam estimativas de desempenho em dados externos.

### 4.4 Robustez das classificações

- Estabilidade de 98,21% das decisões majoritárias.
- Apenas 50 sentenças (3,33%) apresentaram empate em pelo menos uma simulação de retirada individual.
- Unanimidade em 31,07% das sentenças.
- Bootstrap com 10.000 replicações para avaliar a precisão e a consistência das estimativas.

Os resultados indicam elevada estabilidade das decisões majoritárias, apesar das divergências observadas entre os anotadores.

## 5. Estrutura do Repositório

```text
capacitismo-linguistico/
│
├── README.md
│
├── anotacao_resultados_compilado.csv
│
└── projeto_experimento.ipynb
```

**Descrição dos arquivos:**

| Arquivo | Descrição |
|---|---|
| `README.md` | Documentação do projeto |
| `anotacao_resultados_compilado.csv` | Dados de anotação humana do Capta-PTBR — Estágio 2 |
| `projeto_experimento.ipynb` | Notebook com processamento, análises estatísticas e visualizações |

## 6. Tecnologias Utilizadas

A análise foi desenvolvida em Python, utilizando:

- **Pandas:** manipulação e organização dos dados.
- **NumPy:** operações numéricas.
- **SciPy:** testes estatísticos.
- **Statsmodels:** regressão logística, testes de concordância e análises inferenciais.
- **Scikit-learn:** métricas de avaliação, incluindo AUROC.
- **Matplotlib:** visualização dos resultados.
- **Jupyter Notebook / Google Colab:** execução dos experimentos.



## 7. Conclusões

Os resultados evidenciam quatro aspectos principais:

1. **Associação lexical:** a presença de termos do dicionário está fortemente associada à classificação de capacitismo, mas não determina sua ocorrência.

2. **Concordância entre anotadores:** a identificação binária apresentou maior concordância, enquanto categoria e polaridade envolveram divergências interpretativas mais expressivas.

3. **Divergências interpretativas:** a presença lexical está associada à discordância, mas outros fatores contextuais e interpretativos também podem contribuir.

4. **Robustez:** as decisões majoritárias apresentaram elevada estabilidade diante da retirada individual de anotadores.

Em conjunto, os resultados reforçam a importância do contexto linguístico e da avaliação humana na identificação do capacitismo, contribuindo para o aprimoramento dos critérios de anotação e validação do Capta-PTBR.

## 8. Limitações

- Dependência da cobertura do dicionário lexical.
- Subjetividade na interpretação de construções linguísticas.
- Variabilidade sociolinguística e contextual.
- Perfil específico dos anotadores.
- Ausência de validação cruzada k-fold nos modelos de regressão logística.
- Necessidade de avaliações adicionais para investigar a generalização dos resultados.


**Palavras-chave:** Capacitismo Linguístico; Português Brasileiro; Processamento de Linguagem Natural; Anotação Humana; Concordância entre Anotadores; Estatística Inferencial; Regressão Logística.
