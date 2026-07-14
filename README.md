# Projeto Final - Análise de Dados de Recursos Humanos

Projeto avaliativo do Módulo 1 do curso de Análise de Dados do SCTEC, desenvolvido com foco em consultas SQL, análise exploratória de dados e visualização de informações de Recursos Humanos.

## Identificação

- **Aluno:** Samuel Bucco
- **Turma:** T2
- **Módulo:** Módulo 1 - Modelagem de Dados
- **Tema:** Visualização de Dados e Business Intelligence
- **Status:** Finalizado

## Objetivo

Analisar dados de Recursos Humanos a partir do esquema **HR (Human Resources)** do FreeSQL, buscando compreender a distribuição dos salários, a relação entre cargos e departamentos e os padrões de remuneração por localização geográfica.

O projeto foi desenvolvido em duas etapas principais:

1. extração dos dados por meio de consultas SQL no FreeSQL;
2. análise exploratória dos arquivos CSV no Python, utilizando estatísticas descritivas e visualizações.

## Perguntas de análise

O projeto busca responder principalmente às seguintes perguntas:

1. Como os salários estão distribuídos entre departamentos e cargos?
2. Quais departamentos e cargos apresentam maiores médias salariais?
3. Como os funcionários e seus salários estão distribuídos geograficamente?
4. Existem salários muito diferentes do padrão observado na base?
5. Os possíveis outliers salariais representam inconsistências ou diferenças explicáveis por cargo/departamento?

## Fonte dos dados

Os dados foram extraídos do esquema **HR** disponibilizado no [FreeSQL](https://freesql.com/).

As principais tabelas utilizadas foram:

| Tabela | Conteúdo principal |
| --- | --- |
| `EMPLOYEES` | Funcionários, cargos, salários, datas de contratação e departamentos |
| `DEPARTMENTS` | Identificação e nome dos departamentos |
| `JOBS` | Cargos e respectivas faixas salariais |
| `LOCATIONS` | Cidades, estados ou províncias e países |
| `COUNTRIES` | Países e suas regiões |
| `REGIONS` | Identificação e nome das regiões |

## Consultas SQL

Foram criadas duas consultas SQL conforme as orientações do projeto.

### Query 1 - Funcionários, salários, departamentos e cargos

A primeira consulta relaciona as tabelas `EMPLOYEES`, `DEPARTMENTS` e `JOBS` por meio de `LEFT JOIN`.

O objetivo dessa query é reunir informações dos funcionários, seus salários, departamentos e cargos, permitindo analisar a distribuição salarial por área e função.

Arquivo SQL:

```text
sql/query_01.sql
```

Arquivo exportado:

```text
data/query_01.csv
```

### Query 2 - Funcionários, salários e distribuição geográfica

A segunda consulta relaciona as tabelas `EMPLOYEES`, `DEPARTMENTS`, `LOCATIONS`, `COUNTRIES` e `REGIONS` por meio de `LEFT JOIN`.

O objetivo dessa query é analisar os funcionários, seus salários e sua distribuição por cidade, país e região.

Arquivo SQL:

```text
sql/query_02.sql
```

Arquivo exportado:

```text
data/query_02.csv
```

## Análise em Python

A análise exploratória foi desenvolvida no notebook:

```text
notebooks/analise_rh.ipynb
```

As principais etapas realizadas foram:

- importação dos arquivos CSV gerados no FreeSQL;
- verificação inicial da estrutura dos dados;
- análise de valores ausentes e registros duplicados;
- conversão de tipos de dados, incluindo datas e colunas de identificação;
- cálculo de estatísticas descritivas da coluna de salários;
- análise salarial por departamento;
- análise salarial por cargo;
- análise salarial por região, país e cidade;
- criação de visualizações com histogramas, gráficos de barras e boxplots;
- identificação e interpretação de possíveis outliers salariais.

## Resultados e insights

A análise exploratória permitiu identificar alguns padrões relevantes na base de Recursos Humanos.

Entre os principais resultados observados, destacam-se:

- a distribuição salarial apresenta concentração em faixas menores, com poucos funcionários recebendo salários mais elevados;
- existem diferenças salariais relevantes entre departamentos e cargos;
- cargos com maior responsabilidade tendem a apresentar médias salariais mais altas;
- a análise geográfica permite observar a distribuição de funcionários e salários entre regiões, países e cidades;
- foi identificado um outlier na análise geral dos salários;
- ao segmentar a análise por departamento, também foram identificados outliers específicos em algumas áreas;
- o departamento `Shipping` apresentou o maior número de outliers na análise por departamento;
- no departamento `Shipping`, os outliers estão associados principalmente a diferenças de cargo;
- funcionários com o cargo `Stock Manager` apresentam salários mais elevados dentro do departamento `Shipping`.

Esses resultados indicam que os outliers encontrados não devem ser interpretados automaticamente como erros na base. No caso analisado, eles parecem estar relacionados a diferenças reais de cargo, responsabilidade e estrutura salarial.

## Estrutura do projeto

```text
Projeto_Final_Modulo_01_SCTEC/
├── data/
│   ├── query_01.csv
│   └── query_02.csv
├── notebooks/
│   └── analise_rh.ipynb
├── sql/
│   ├── query_01.sql
│   └── query_02.sql
├── README.md
└── requirements.txt
```

## Tecnologias utilizadas

- SQL;
- FreeSQL;
- Python;
- Pandas;
- Matplotlib;
- Seaborn;
- Jupyter Notebook;
- Git e GitHub.

## Como executar o projeto

Para reproduzir a análise, siga os passos abaixo.

1. Clone o repositório:

```bash
git clone https://github.com/samuelbucco/Projeto_Final_Modulo_01_SCTEC.git
```

2. Acesse a pasta do projeto:

```bash
cd Projeto_Final_Modulo_01_SCTEC
```

3. Instale as dependências:

```bash
pip install -r requirements.txt
```

4. Abra o notebook:

```text
notebooks/analise_rh.ipynb
```

5. Execute as células do notebook em ordem.

Os arquivos CSV necessários para a análise já estão disponíveis na pasta `data/`.

## Acompanhamento do projeto

- [x] Criar e conectar o repositório no GitHub
- [x] Preparar a documentação inicial no README
- [x] Desenvolver a Query 1
- [x] Desenvolver a Query 2
- [x] Exportar os resultados para CSV
- [x] Importar e verificar os dados no Python
- [x] Realizar a análise exploratória
- [x] Calcular as estatísticas descritivas
- [x] Criar os gráficos
- [x] Identificar e interpretar outliers
- [x] Registrar os resultados e insights no README
- [x] Revisar a organização e a reprodutibilidade do projeto
- [x] Gravar o vídeo de apresentação
- [x] Publicar e enviar os links no AVA

## Possíveis melhorias futuras

- ampliar as análises com novas variáveis do esquema HR;
- criar visualizações interativas;
- automatizar a extração e atualização dos dados;
- desenvolver um dashboard para acompanhamento dos indicadores de RH;
- comparar salários com as faixas mínimas e máximas previstas na tabela `JOBS`.

## LINKS

- Repositório: https://github.com/samuelbucco/Projeto_Final_Modulo_01_SCTEC.git
- Vídeo: https://www.loom.com/share/c66fbd1653f547d58dd7af62311ef1f5

