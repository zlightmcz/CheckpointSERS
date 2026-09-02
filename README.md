# CheckpointSERS

# Desafio Final — Análise de Dados de Energia

## Sobre o projeto

Este projeto apresenta uma atividade prática de **Análise de Dados de Energia**, desenvolvida no curso de **Ciência da Computação**, na disciplina de **Soluções em Energias Renováveis e Sustentáveis**.

A atividade tem como objetivo analisar diferentes conjuntos de dados relacionados ao consumo e à geração de energia, aplicando técnicas de organização, tratamento, filtragem, análise estatística e visualização de dados.

Durante o projeto são utilizados dados provenientes de fontes públicas, como o **Operador Nacional do Sistema Elétrico (ONS)**, o **UCI Machine Learning Repository** e o **Kaggle**.

Todo o desenvolvimento, incluindo códigos, resultados, gráficos e interpretações, permanece no Notebook da atividade.

---

## Objetivo

O objetivo principal é utilizar ferramentas de programação para analisar dados reais relacionados à energia e identificar padrões de consumo e geração.

Entre as principais atividades realizadas estão:

* Organização dos dados;
* Criação e manipulação de DataFrames;
* Verificação de valores ausentes;
* Tratamento e análise das variáveis;
* Cálculo de indicadores estatísticos;
* Identificação de períodos de alta demanda;
* Criação de filtros e recortes específicos;
* Produção de gráficos;
* Interpretação dos resultados;
* Criação de um resumo final das análises.

---

## Situação-problema

Uma equipe de planejamento energético precisa analisar o comportamento da carga elétrica de uma região atendida pelo **Sistema Interligado Nacional (SIN)**.

Para isso, os dados são obtidos por meio da API pública de **Carga Verificada do ONS**. A partir dos dados coletados, são realizadas etapas de preparação e análise, incluindo a criação de DataFrames, organização das informações, identificação de valores ausentes, cálculo de indicadores estatísticos, criação de recortes e produção de gráficos.

Além da análise da carga elétrica, o projeto utiliza outros conjuntos de dados relacionados ao consumo residencial, consumo industrial, distribuição de energia e geração de energia solar.

---

# Fontes dos dados

## ONS — Operador Nacional do Sistema Elétrico

A análise da carga elétrica utiliza a API pública de **Carga Verificada do ONS**.

**Portal de dados:**
https://dados.ons.org.br/

**Dataset utilizado:**
https://dados.ons.org.br/dataset/carga-energia-verificada

A análise utiliza inicialmente os dados referentes à área **SP — São Paulo**, no período de **01/08/2025 a 07/08/2025**.

---

## UCI Machine Learning Repository

Foram utilizados quatro conjuntos de dados provenientes do **UCI Machine Learning Repository**.

### Appliances Energy Prediction

Utilizado para identificar períodos de consumo elevado de eletrodomésticos e verificar quais condições de temperatura estavam presentes nesses momentos.

**Fonte:** UCI Machine Learning Repository.

### Steel Industry Energy Consumption

Utilizado para localizar situações de consumo elevado em uma indústria siderúrgica e verificar se esses períodos coincidem com carga máxima ou fator de potência mais baixo.

**Fonte:** UCI Machine Learning Repository.

### Power Consumption of Tetouan City

Utilizado para identificar qual zona apresenta o maior pico de consumo e verificar as condições de temperatura nos momentos de maior demanda.

**Fonte:** UCI Machine Learning Repository.

### Individual Household Electric Power Consumption

Utilizado para identificar episódios de potência ativa elevada que também apresentem corrente acima do comportamento médio.

**Fonte:** UCI Machine Learning Repository.

---

## Kaggle

### Solar Power Generation Data

Utilizado para analisar a geração de energia de uma usina fotovoltaica, buscando localizar períodos de alta geração e identificar os inversores mais frequentes nesses momentos.

A análise é realizada sem realizar junção com o arquivo de sensores.

**Fonte:** Kaggle.

---

# Etapas da análise

## 1. Organização dos dados

Os dados são inicialmente preparados para permitir sua análise.

Nesta etapa são realizadas atividades como:

* Renomeação dos principais atributos;
* Criação de DataFrames com os atributos necessários;
* Verificação de valores ausentes;
* Contagem de valores ausentes nos atributos relevantes;
* Verificação do formato numérico das variáveis;
* Verificação do formato das datas e horários;
* Registro das decisões de tratamento dos dados.

---

## 2. Indicadores da carga elétrica

São calculados os principais indicadores estatísticos da carga:

* Carga mínima;
* Carga máxima;
* Carga média;
* Mediana;
* Amplitude entre o máximo e o mínimo;
* Quantidade total de medições.

Com esses indicadores, é analisado se o valor máximo está muito distante do comportamento médio observado.

---

## 3. Períodos de alta demanda

Para identificar períodos de alta demanda, são considerados os registros cuja carga seja superior a **90% da carga máxima**.

Nesta etapa são realizados:

* Cálculo do limiar de alta demanda;
* Criação de um DataFrame com os registros acima do limiar;
* Contagem dos registros selecionados;
* Cálculo do percentual em relação ao total;
* Identificação do maior valor de carga;
* Identificação da data e horário do pico, quando disponíveis.

---

## 4. Segundo critério de análise

Também é criado um segundo recorte utilizando um critério definido para a análise.

Entre os critérios possíveis estão:

* Carga acima da média;
* Carga abaixo de uma porcentagem do máximo;
* Intervalo específico de valores;
* Determinado dia ou período;
* Combinação de duas condições.

Após a aplicação do critério, são analisados:

* Critério utilizado;
* DataFrame resultante;
* Quantidade de registros;
* Percentual em relação ao total;
* Comparação com o conjunto de alta demanda.

---

## 5. Visualização dos dados

São construídos pelo menos dois gráficos para auxiliar na interpretação dos dados.

Um dos gráficos representa o comportamento da carga ao longo das observações ou do tempo.

O segundo gráfico é escolhido de acordo com o objetivo da análise.

Os gráficos apresentam:

* Título;
* Eixos;
* Unidades, quando aplicável;
* Interpretação dos resultados.

---

# Síntese dos resultados

Ao final da análise é criada a variável `resumo_resultados`, contendo os principais resultados obtidos.

A variável reúne informações como:

* Região;
* Período;
* Quantidade de registros;
* Carga mínima;
* Carga máxima;
* Carga média;
* Mediana;
* Limiar de alta demanda;
* Quantidade de registros de alta demanda;
* Percentual de alta demanda;
* Momento do pico;
* Resultado do segundo critério.

A IA é utilizada como apoio na interpretação dos resultados, recebendo os dados produzidos pela equipe sem substituir a análise realizada.

---

# Tecnologias e bibliotecas

O projeto foi desenvolvido utilizando **Python** e as seguintes bibliotecas:

### Pandas

Utilizada para manipulação, organização, filtragem e análise dos dados por meio de DataFrames.

### Matplotlib

Utilizada para criação dos gráficos e visualização dos resultados.

### Re

Utilizada para operações de tratamento e manipulação de textos por meio de expressões regulares.

### Unicodedata

Utilizada para normalização e tratamento de caracteres.

### IPython

Utilizada para facilitar a apresentação dos DataFrames e resultados dentro do Notebook.

---

# Datasets analisados

| Dataset                                         | Fonte  | Objetivo                                                   |
| ----------------------------------------------- | ------ | ---------------------------------------------------------- |
| Carga Verificada                                | ONS    | Analisar o comportamento da carga elétrica em São Paulo    |
| Appliances Energy Prediction                    | UCI    | Analisar o consumo de eletrodomésticos                     |
| Steel Industry Energy Consumption               | UCI    | Analisar o consumo de energia de uma indústria siderúrgica |
| Power Consumption of Tetouan City               | UCI    | Analisar o consumo de energia de diferentes zonas          |
| Solar Power Generation Data                     | Kaggle | Analisar a geração de energia solar                        |
| Individual Household Electric Power Consumption | UCI    | Analisar o consumo de energia de uma residência            |

---

# Conclusão

Os exercícios realizados utilizam diferentes conjuntos de dados relacionados ao consumo e à geração de energia para aplicar técnicas de análise e visualização de dados.

A utilização de limites proporcionais aos próprios dados permite identificar eventos de maior consumo ou geração. A inclusão de uma segunda condição torna os recortes mais específicos e possibilita comparações entre diferentes situações.

As conclusões devem ser interpretadas considerando o contexto e as características de cada dataset, sem extrapolar os resultados para situações que não estejam representadas nas bases analisadas.

O projeto demonstra a aplicação prática de **Python, Pandas e Matplotlib** na análise de dados relacionados ao setor energético.
