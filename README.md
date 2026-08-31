# Análise de Mortalidade — Janeiro a Maio de 2026

## 📌 Sobre o projeto

Este projeto foi desenvolvido como trabalho final da disciplina **DS-PY-004 — Análise exploratória de dados com Python, NumPy, Pandas e Git**.

O objetivo é realizar uma análise exploratória de uma base real de mortalidade, passando pelas etapas de carregamento, diagnóstico, limpeza, transformação e análise dos dados, buscando identificar padrões e características dos óbitos registrados no período analisado.

A análise utiliza **Python, Pandas, NumPy e Matplotlib**, além do controle de versão com Git e GitHub.

---

## 📊 Base de dados

A base utilizada contém registros de mortalidade e apresenta informações relacionadas às características dos óbitos, como:

* data do óbito;
* data de nascimento;
* sexo;
* raça/cor;
* idade;
* município;
* estado;
* causa básica do óbito;
* entre outras informações.

O recorte analisado corresponde aos **óbitos registrados entre janeiro e maio de 2026**.

A base original é uma base pública e foi utilizada em seu formato bruto para que fossem realizadas as etapas de diagnóstico e tratamento dos dados.

Como a base possui tamanho elevado, o arquivo original não é armazenado diretamente no repositório.

---

## 🎯 Perguntas da análise

A análise busca compreender os principais padrões presentes nos registros de mortalidade, especialmente:

1. Como os óbitos se distribuem ao longo dos meses analisados?
2. Como os óbitos se distribuem de acordo com a idade e a faixa etária?
3. Existem diferenças na distribuição dos óbitos entre os sexos?
4. Quais são as principais causas de morte identificadas na base?
5. Como os óbitos se distribuem geograficamente entre estados e municípios?

Além dessas perguntas principais, foram realizadas análises complementares para avaliar a qualidade dos dados e identificar valores extremos na variável idade.

---

## 🔎 Diagnóstico dos dados

Antes da análise, foi realizada uma etapa de diagnóstico da qualidade da base.

Foram avaliados:

* quantidade de linhas e colunas;
* tipos das variáveis;
* valores ausentes;
* registros duplicados;
* distribuição das categorias;
* valores extremos da variável idade;
* consistência das informações após operações de transformação e `merge`.

A análise de valores ausentes permitiu identificar quais variáveis apresentavam dados faltantes e orientar as decisões tomadas durante a etapa de tratamento.

Também foram analisados possíveis valores extremos de idade utilizando **IQR (Intervalo Interquartil)** e **z-score**.

Os valores identificados como extremos não foram automaticamente considerados erros, uma vez que valores extremos podem representar características reais da população analisada.

---

## 🧹 Limpeza e transformação

Após o diagnóstico, foram realizadas transformações para facilitar a análise.

Entre os tratamentos realizados estão:

* padronização da variável sexo;
* padronização da variável raça/cor;
* tratamento de valores ignorados;
* transformação da idade para anos;
* criação de faixas etárias;
* criação da variável mês do óbito;
* cálculo do z-score da idade;
* consolidação de informações provenientes de tabelas auxiliares.

Foram utilizadas diferentes ferramentas do ecossistema Python, incluindo:

* `map()`;
* `apply()`;
* `pd.cut()`;
* `groupby()`;
* `merge()`;
* `pivot_table()`;
* operações vetorizadas com NumPy.

Durante os `merge`s realizados, foi feita a conferência da quantidade de registros antes e depois da operação para verificar se houve perda ou duplicação de linhas.

---

## 📈 Análise exploratória

A análise exploratória buscou identificar padrões relacionados ao período, perfil das pessoas e causas dos óbitos.

Foram produzidas visualizações para analisar:

* quantidade de mortes por mês;
* idade média e mediana;
* distribuição dos óbitos por estado;
* principais causas de morte;
* distribuição por faixa etária e sexo;
* municípios com maior quantidade de registros;
* óbitos por 100 mil habitantes;
* distribuição da idade.

Os gráficos são acompanhados de interpretações dos principais padrões observados nos dados.

---

## 🧮 Principais análises

### Distribuição temporal

Foi analisada a quantidade de óbitos registrados em cada mês do período de janeiro a maio de 2026, permitindo observar como os registros se distribuíram ao longo do período.

### Perfil etário

A idade dos indivíduos foi analisada por meio de medidas como média, mediana e desvio padrão, além da criação de faixas etárias para facilitar a interpretação da distribuição dos óbitos.

### Sexo

Os registros foram classificados em:

* Masculino;
* Feminino;
* Ignorado.

A distribuição entre os sexos foi analisada de forma geral e também em conjunto com as faixas etárias.

### Causas de morte

As causas básicas de morte foram analisadas a partir dos códigos CID, permitindo identificar as causas com maior frequência entre os registros.

### Distribuição geográfica

Foram analisados os estados e municípios associados aos registros de óbito.

Também foi realizada uma análise utilizando a população dos municípios para calcular uma medida de óbitos por 100 mil habitantes. Essa medida é uma **taxa bruta referente ao período analisado**, não uma taxa anual de mortalidade.

---

## 📌 Principais conclusões

A análise permitiu identificar diferenças na distribuição dos óbitos segundo período, idade, sexo, causas e localização geográfica.

Entre os principais achados estão:

* a distribuição dos óbitos apresenta variações entre os meses analisados;
* a idade dos indivíduos apresenta uma distribuição heterogênea, com concentração em determinadas faixas etárias;
* existem diferenças na distribuição dos óbitos entre homens e mulheres, inclusive quando observadas por faixa etária;
* algumas causas de morte apresentam frequência significativamente maior que outras;
* a análise por município apresenta resultados diferentes quando se considera o tamanho da população, evidenciando a importância de utilizar taxas além de números absolutos.

---

## ⚠️ Limitações

Os resultados devem ser interpretados considerando algumas limitações da análise.

O período analisado corresponde somente aos meses de **janeiro a maio de 2026**, portanto os resultados não devem ser interpretados como representativos de todo o ano.

Além disso, as taxas calculadas por município são taxas brutas baseadas na população utilizada como referência e não consideram diferenças na estrutura etária ou outras características demográficas das populações.

A análise também identifica associações e padrões nos dados, mas não permite estabelecer relações de causalidade.

---

## 🔭 Próximos passos

Com mais tempo e dados, algumas análises poderiam ser aprofundadas, como:

* ampliar o período para incluir anos anteriores;
* comparar a mortalidade entre diferentes anos;
* analisar a evolução das principais causas de morte ao longo do tempo;
* aprofundar a análise regional;
* utilizar taxas padronizadas por idade;
* investigar diferenças socioeconômicas e demográficas associadas aos óbitos.

---

## 🛠️ Tecnologias utilizadas

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Jupyter Notebook**
* **Git**
* **GitHub**

---

## 📁 Estrutura do projeto

```text
projeto/
├── README.md
├── notebooks/
│   └── analise_mortalidade_JAN_MAI_2026.ipynb
├── dados/
│   └── (base de dados ou referência para acesso à base)
└── .gitignore
```

---

## ▶️ Como reproduzir a análise

1. Clone este repositório:

```bash
git clone <URL_DO_REPOSITORIO>
```

2. Entre na pasta do projeto:

```bash
cd <NOME_DO_REPOSITORIO>
```

3. Instale as bibliotecas utilizadas:

```bash
pip install pandas numpy matplotlib jupyter
```

4. Abra o Jupyter Notebook:

```bash
jupyter notebook
```

5. Acesse o notebook localizado na pasta `notebooks/` e execute as células na ordem apresentada.

> **Observação:** a base original possui tamanho elevado e, por isso, não é armazenada diretamente no GitHub. É necessário disponibilizar a base no local indicado pelo notebook antes de executar a análise.

---

## 👥 Trabalho em grupo

Projeto desenvolvido em grupo como atividade final da disciplina **DS-PY-004**.

O histórico de commits do repositório apresenta a participação dos integrantes no desenvolvimento do projeto.
