# 🚀 Projeto_MVP_Engenharia_de_Dados

📌 Descrição

Este projeto tem como foco analisar os chamados registrados na plataforma 311 da cidade de Nova York no ano de 2024, utilizando Databricks, PySpark e SQL para processar e transformar os dados. O intuito é construir um pipeline de dados estruturado nas camadas Bronze, Silver e Gold, permitindo avaliar a eficiência dos atendimentos por agência.

📁 Estrutura do Projeto

1️⃣ Ingestão de Dados: Importação dos arquivos CSV contendo os atendimentos e suas respectivas informações.

2️⃣ Transformação e Limpeza: Padronização de colunas, tratamento de valores nulos e formatação das datas.

3️⃣ Modelagem de Dados (Esquema Estrela):

  * Tabela Fato (Fato_Unique_Key): Contém os dados principais dos atendimentos.

  * Tabelas Dimensão:
    * Dim_Agencia: Informações sobre as agências que mais tiveram atendimentos
    
    * Dim_Tempo: Detalhes temporais dos atendimentos.
      

🌟 Esquema Estrela

As tabelas estão estruturadas da seguinte forma:

#### 🗂️ Tabela Fato: `Fato_Atendimentos`

| 🏷️ Coluna                 | 📌 Tipo  | 🔑 Chave            | 📖 Descrição                              |
|---------------------------|---------|---------------------|------------------------------------------|
| ID_Unique_Key            | STRING  | PK               | Identificador único do atendimento      |
| ID_Agencia               | STRING  | 🔗 FK → Dim_Agencia | Identificador da agência responsável    |
| ID_Data                  | STRING  | 🔗 FK → Dim_Tempo   | Identificador da data do atendimento    |
| Execution_Time_Seconds   | INT     | -                   | Tempo total do atendimento (em segundos) |
| Status                   | STRING  | -                   | Status do chamado                       |

#### 🗂️ Tabela Dimensão: `Dim_Agencia`

| 🏷️ Coluna   | 📌 Tipo  | 🔑 Chave  | 📖 Descrição                  |
|------------|---------|----------|--------------------------------|
| ID_Agencia | STRING  | PK    | Identificador único da agência |
| Agency     | STRING  | -        | Sigla da agência              |
| Agency_Name| STRING  | -        | Nome completo da agência      |

#### 🗂️ Tabela Dimensão: `Dim_Tempo`

| 🏷️ Coluna        | 📌 Tipo  | 🔑 Chave  | 📖 Descrição                           |
|------------------|---------|----------|---------------------------------------|
| ID_Data        | STRING  | PK       | Identificador único da data (YYYYMMDD) |
| Ano            | INT     | -        | Ano do atendimento                    |
| Mês            | INT     | -        | Mês do atendimento                    |
| Dia            | INT     | -        | Dia do atendimento                    |
| Dia_da_Semana  | STRING  | -        | Nome do dia da semana                 |


🛠️ Tecnologias Utilizadas:

💾 Databricks para processamento e armazenamento.

🔥 PySpark para processamento distribuído.

🛢️ SQL para consultas

🔮 Possíveis Melhorias Futuras
✨ Implementação de pipeline automatizado para atualização dos dados.
📊 Criação de dashboards para visualização dos KPIs de atendimento.

---

Observações:

Este repositório contém dois notebooks:


- *Notebook Databricks* (.dbc): otimizado para ser importado diretamente no Databricks, com todas as células já executadas.
- *Notebook em Python* (.ipynb): pode ser executado em Jupyter, Google Colab ou reimportado no Databricks.


## 1. Importar o Notebook Databricks

Para visualizar e executar o notebook diretamente no Databricks:

1️⃣ Baixe o arquivo [Projeto_MVP_Engenharia_de_Dados.dbc](Projeto_MVP_Engenharia_de_Dados.dbc)

2️⃣ Acesse seu workspace Databricks.

3️⃣ No menu à esquerda, vá até a aba *Workspace*.

4️⃣ Clique com o botão direito sobre a pasta onde deseja importar > *Import*.

5️⃣ Selecione o arquivo .dbc e clique em *Import*.

6️⃣ O notebook será exibido com *todos os outputs salvos* e estará pronto para *reexecução* se necessário.

---

## 2. Executar o Notebook em Python (Google Colab)

1️⃣ Importar os dados no Databricks;

2️⃣ Executar todos os códigos;

3️⃣ Validar os Resultados.

4️⃣ Clique no botão abaixo para abrir diretamente no Google Colab:

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/HuriAnn/mvp-chamados-analytics/blob/main/Projeto_MVP_Engenharia_de_Dados.ipynb)

