🚀 Projeto_MVP_Engenharia_de_Dados

📌 Descrição
Este projeto tem como objetivo a modelagem e estruturação de um esquema estrela para análise de atendimentos realizados por agências. Utiliza dados de chamadas de serviço e processa informações para a camada Gold, garantindo uma estrutura otimizada para consultas e análises.

📁 Estrutura do Projeto
O projeto está dividido nas seguintes etapas:

1️⃣ Ingestão de Dados: Importação dos arquivos CSV contendo os atendimentos e suas respectivas informações.
2️⃣ Transformação e Limpeza: Padronização de colunas, tratamento de valores nulos e formatação das datas.
3️⃣ Modelagem de Dados (Esquema Estrela):
🔹 Tabela Fato (Fato_Atendimentos): Contém os dados principais dos atendimentos.
🔹 Tabelas Dimensão:

🏢 Dim_Agencia: Informações sobre as agências responsáveis pelos atendimentos.

📅 Dim_Tempo: Detalhes temporais dos atendimentos.
4️⃣ Criação da Camada Gold: Consolida os dados transformados para uma visão final otimizada.

🌟 Esquema Estrela
As tabelas estão estruturadas da seguinte forma:

🗂️ Tabela Fato: Fato_Atendimentos
🏷️ Coluna	📌 Tipo	🔑 Chave	📖 Descrição
ID_Atendimento	STRING	🔑 PK	Identificador único do atendimento
ID_Agencia	STRING	🔗 FK → Dim_Agencia	Identificador da agência responsável
ID_Data	STRING	🔗 FK → Dim_Tempo	Identificador da data do atendimento
Execution_Time_Seconds	INT	-	Tempo total do atendimento (em segundos)
Status	STRING	-	Status do chamado
🏢 Tabela Dimensão: Dim_Agencia
🏷️ Coluna	📌 Tipo	🔑 Chave	📖 Descrição
ID_Agencia	STRING	🔑 PK	Identificador único da agência
Agency	STRING	-	Sigla da agência
Agency_Name	STRING	-	Nome completo da agência
📅 Tabela Dimensão: Dim_Tempo
🏷️ Coluna	📌 Tipo	🔑 Chave	📖 Descrição
ID_Data	STRING	🔑 PK	Identificador único da data (YYYYMMDD)
Ano	INT	-	Ano do atendimento
Mês	INT	-	Mês do atendimento
Dia	INT	-	Dia do atendimento
Dia_da_Semana	STRING	-	Nome do dia da semana
⚙️ Como Executar
1️⃣ Configurar o Ambiente:

Importar os dados no Databricks.

Criar as tabelas na camada Gold.
2️⃣ Rodar os Scripts:

Executar as transformações e modelagens.

Criar as tabelas fato e dimensões.
3️⃣ Validar os Resultados:

🔍 Verificar a consistência dos dados processados.

📊 Avaliar a qualidade das chaves primárias e estrangeiras.

🛠️ Tecnologias Utilizadas
💾 Databricks para processamento e armazenamento.

🔥 PySpark para processamento distribuído.

SQL para consultas

🔮 Possíveis Melhorias Futuras
✨ Implementação de pipeline automatizado para atualização dos dados.
📊 Criação de dashboards para visualização dos KPIs de atendimento.
