### Análise de Mortalidade Geral (2026)

Este projeto apresenta uma análise estatística e exploratória dos dados de óbitos no Brasil referentes aos primeiros meses do ano de 2026. O objetivo é responder a perguntas de negócio sobre o perfil demográfico, temporal, geográfico e clínico das ocorrências, utilizando as bibliotecas pandas, matplotlib e numpy. 

### 📂 Arquivos Utilizados

O projeto cruza os dados brutos de mortalidade com tabelas auxiliares de dicionários: 

* MORTALIDADE_GERAL_2026.csv: Base bruta de óbitos (uma linha por registro).
* MUNICIPIOS.xlsx: Dicionário com códigos IBGE, nomes de municípios, estados (UF) e população.
* CIDs_com_descricao.xlsx: Dicionário com a descrição médica dos códigos da CID-10.

### 🔍 Perguntas Respondidas

1. **Quantidade de mortes por mês**.
2. **Média, mediana e desvio padrão** da idade por mês.
3. **Quantidade de mortes por estado**.
4. **Quantidade de mortes por CID** (Código Internacional de Doenças).
5. **As 10 maiores causas de morte** e o percentual de impacto de cada uma.
6. **Quantidade de mortes por faixa de idade**.
7. **As 10 cidades onde mais pessoas morreram** (métricas absolutas).
8. **Percentual de óbitos por população** (métrica proporcional por 100 mil habitantes).
9. **Análise estatística da idade**: Cálculo do IQR (Intervalo Interquartil), Histograma e geração da coluna de *Z-Score*.

### 🛠️ Tecnologias e Técnicas Aplicadas

* **Tratamento de Dados (pandas)**: Limpeza de duplicatas, preenchimento de campos (zfill), engenharia de recursos para extração de datas/meses e conversão programática da codificação original de idade do sistema SIM para anos de vida.
* **Cruzamento de Dados (merge)**: Relacionamento da base principal com tabelas auxiliares através de chaves estrangeiras (CODMUNOCOR e CAUSABAS), simulando a lógica de um *PROCV*.
* **Estatística Computacional (numpy)**: Utilizado para extração de percentis, cálculo do IQR e padronização de dados através do *Z-Score*.
* **Visualização de Dados (matplotlib / seaborn)**: Geração de gráficos de linha e barras para evidenciar tendências sazonais e demográficas.

### 📈 Principais Insights Obtidos

* **Sazonalidade Temporal**: Os meses de janeiro a abril mantêm um volume linear de óbitos, enquanto maio apresenta uma queda abrupta, o que evidencia que a base de dados ainda era preliminar e estava incompleta para este mês específico no momento da extração.
* **Perfil Demográfico**: A idade mediana dos óbitos se concentra estavelmente entre 71 e 72 anos. Mais de 70% dos registros pertencem à faixa de 60 anos ou mais.
* **Morbidade Líder**: O *Infarto agudo do miocárdio* é a maior causa isolada de morte (representando cerca de 5,37% do total), seguido de perto por *Pneumonia* (3,99%).
* **Visão Absoluta vs. Proporcional**: Embora grandes capitais liderem em números absolutos de mortes devido ao tamanho de suas populações, o cálculo proporcional por 100 mil habitantes revela que municípios de pequeno porte do interior do país registraram os maiores índices de mortalidade proporcional no período.

### 🛑 Limitações do Estudo

* **Recorte Temporal Restrito**: A base de dados compreende apenas o período de 01/01/2026 a 31/05/2026, inviabilizando previsões sazonais completas para o restante do ano (como o impacto total do inverno).
* **Métricas Brutas**: As taxas proporcionais calculadas por município são brutas, não considerando o envelhecimento populacional ou a padronização por pirâmide etária.
* **Subnotificação**: A presença de "Outras causas mal definidas" no Top 3 de CIDs indica possíveis atrasos de fechamento ou falhas no preenchimento de laudos médicos na base original.