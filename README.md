# Projeto Final - Análise de Dados de Recursos Humanos

Projeto avaliativo do Módulo 1 do curso de Análise de Dados do SCTEC.

## Identificação

- **Aluno:** Samuel Bucco
- **Turma:** T2
- **Módulo:** Módulo 1 - Modelagem de Dados
- **Tema:** Visualização de Dados e Business Intelligence
- **Status:** Em desenvolvimento

## Objetivo

Analisar dados de Recursos Humanos para compreender a distribuição dos salários, a relação entre cargos e departamentos e os padrões de remuneração por região.

Os dados serão consultados no esquema **HR (Human Resources)** do banco FreeSQL. Os resultados das consultas SQL serão exportados para arquivos CSV e analisados em Python por meio de estatísticas descritivas e visualizações.

## Perguntas de análise

O projeto busca responder principalmente às seguintes perguntas:

1. Como os salários estão distribuídos entre os departamentos e cargos?
2. Como os funcionários e seus salários estão distribuídos geograficamente?
3. Existem salários muito diferentes do padrão observado em cada grupo?
4. Quais departamentos, cargos ou regiões apresentam os maiores e menores salários?

## Fonte dos dados

Será utilizado o esquema **HR** disponibilizado no [FreeSQL](https://freesql.com/). As principais tabelas previstas são:

| Tabela | Conteúdo principal |
| --- | --- |
| `EMPLOYEES` | Funcionários, cargos, salários e departamentos |
| `DEPARTMENTS` | Identificação e nome dos departamentos |
| `JOBS` | Cargos e respectivas faixas salariais |
| `LOCATIONS` | Cidades, estados ou províncias e países |
| `COUNTRIES` | Países e suas regiões |
| `REGIONS` | Identificação e nome das regiões |

## Consultas SQL planejadas

### Query 1 - Salário por departamento e cargo

A primeira consulta relacionará `EMPLOYEES`, `DEPARTMENTS` e `JOBS` utilizando `LEFT JOIN`. O objetivo será reunir os dados necessários para comparar salários entre departamentos e cargos.

O resultado será exportado para `query_01.csv`.

### Query 2 - Funcionários por região

A segunda consulta relacionará `EMPLOYEES`, `DEPARTMENTS`, `LOCATIONS`, `COUNTRIES` e `REGIONS` utilizando `LEFT JOIN`. O objetivo será analisar a distribuição dos funcionários e salários por cidade, estado ou província, país e região.

O resultado será exportado para `query_02.csv`.

## Análise em Python

Os arquivos CSV serão importados no Python para uma Análise Exploratória de Dados (EDA). Estão previstas as seguintes etapas:

- verificação da estrutura e da qualidade dos dados;
- identificação de valores ausentes e registros duplicados;
- cálculo de média, mediana, valor mínimo e valor máximo;
- comparação dos salários por departamento, cargo e região;
- identificação e interpretação de possíveis outliers;
- criação de histogramas e/ou boxplots.

Os principais resultados e insights serão incluídos neste README após a conclusão das análises.

## Estrutura planejada do projeto

```text
Projeto_Final_Modulo_01_SCTEC/
├── data/
│   ├── query_01.csv
│   └── query_02.csv
├── notebooks/
│   └── notebook_queries.ipynb
|   └── analise_rh.py
├── sql/
│   └── queries.sql
├── images/
│   └── graficos_do_projeto.png
├── README.md
└── requirements.txt
```

> Os diretórios e arquivos serão adicionados conforme o desenvolvimento do projeto.

## Tecnologias previstas

- SQL e FreeSQL;
- Python;
- Pandas;
- Matplotlib;
- Seaborn;
- Jupyter Notebook;
- Git e GitHub.

## Como executar

As instruções completas serão atualizadas conforme o projeto avançar. Inicialmente, será necessário ter o Python instalado e instalar as dependências com:

```bash
pip install -r requirements.txt
```

Depois da inclusão dos arquivos de dados e scripts, esta seção apresentará o passo a passo completo para reproduzir as análises.

## Acompanhamento do projeto

- [x] Criar e conectar o repositório no GitHub
- [x] Preparar a documentação inicial no README
- [ ] Desenvolver a Query 1
- [ ] Desenvolver a Query 2
- [ ] Exportar os resultados para CSV
- [ ] Importar e verificar os dados no Python
- [ ] Realizar a análise exploratória
- [ ] Calcular as estatísticas descritivas
- [ ] Criar os gráficos
- [ ] Registrar os resultados e insights no README
- [ ] Revisar a organização e a reprodutibilidade do projeto
- [ ] Gravar o vídeo de apresentação
- [ ] Publicar e enviar os links no AVA

## Resultados e insights

Esta seção será preenchida após a execução das consultas e da análise exploratória.

## Possíveis melhorias futuras

- ampliar as análises com novas variáveis do esquema HR;
- criar visualizações interativas;
- automatizar a extração e atualização dos dados;
- desenvolver um dashboard para acompanhamento dos indicadores de RH.
