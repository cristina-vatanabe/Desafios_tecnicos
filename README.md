# 📊 Desafios Técnicos — Análise de Dados

Repositório dedicado ao desenvolvimento e entrega dos desafios técnicos do bootcamp de **Análise de Dados**. Todos os projetos estão ancorados no domínio de negócio **Atendimento ao Cliente**, evoluindo desde a geração e integração automatizada de bases via API até a análise estatística descritiva para tomada de decisão.

---

## 📁 Estrutura do Repositório

```text
Desafios_tecnicos/
├── Desafio1_API_Python.ipynb                      # Integração com Google Sheets API e geração de dados mockados
├── Desafio2_Estatistica_Python.ipynb              # Análise estatística descritiva e diagnóstico operacional
├── Desafio_01_Atendimento_Cliente - clientes.csv  # Amostra da tabela dimensão gerada via Python/Faker
└── README.md                                      # Documentação geral do repositório
🎯 Domínio de Negócio: Atendimento ao Cliente
A escolha do tema Atendimento ao Cliente permite explorar gargalos operacionais comuns a operações de suporte, como SLA, tempo médio de atendimento (TMA), taxa de resolução no primeiro contato (FCR) e comportamento por canal. O modelo de dados segue a arquitetura dimensional (Star Schema simplificado):

Tabela Dimensão (clientes): Cadastro único de clientes (cliente_id, segmento, canal_preferido, data_cadastro).

Tabela Fato (chamados): Registro transacional dos atendimentos, contendo métricas de tempo e resolução.

🚀 Desafios Desenvolvidos
1. Integração com Google Sheets API e Geração de Dados
Arquivo: Desafio1_API_Python.ipynb

Saída gerada: Desafio_01_Atendimento_Cliente - clientes.csv

Objetivos de Aprendizagem e Entregas:

Conceito e Aplicação de APIs: Utilização de APIs como contrato de comunicação entre scripts externos (Google Colab) e serviços em nuvem (Google Workspace) para automatizar pipelines de escrita e leitura de dados.

Autenticação Segura: Configuração de credenciais via Service Account do Google Cloud Platform armazenadas nos Secrets do Google Colab, garantindo que chaves privadas (JSON) não fiquem expostas no código-fonte.

Manipulação de Planilhas via Código: Conexão com a Google Sheets API utilizando a biblioteca gspread para criar cabeçalhos, inserir registros em lote (append_rows) e validar a integridade da escrita em tempo real.

Geração Ética e Reprodutível de Dados Mockados: Uso da biblioteca Faker (com sementes fixas seed(42)) para simular dados sintéticos aderentes ao esquema definido, respeitando boas práticas de governança e privacidade (sem exposição de dados pessoais reais e sem fabricação de estatísticas apresentadas como reais).

2. Relatório de Estatística Descritiva e Insights de Negócio
Arquivo: Desafio2_Estatistica_Python.ipynb

Objetivos de Aprendizagem e Entregas:

Auditoria e Integridade de Dados: Validação de tipos de dados, verificação de valores ausentes, checagem de duplicatas e validação de integridade referencial entre chave estrangeira e primária (cliente_id) antes da modelagem.

Análise Univariada (Tendência Central, Dispersão e Distribuição):

Avaliação da variável tempo_atendimento_min (42.000 registros), identificando assimetria positiva (skewness = 1.39), com média de 15,60 min, mediana de 13,00 min e desvio padrão de 11,28 min.

Tratamento fundamentado de outliers via regra do IQR (1.247 chamados acima de 42,00 min), optando pela manutenção dos registros extremos por representarem casos operacionais reais e críticos.

Cruzamento Dimensional e Diagnóstico de Causa Raiz:

Junção (Left Join) entre fato e dimensão para isolar variáveis de impacto.

Descoberta do principal fator de variação: chamados não resolvidos no primeiro contato apresentam média de 23,46 min, quase o triplo da média dos atendimentos resolvidos de imediato (8,67 min).

Visualização de Dados e Recomendação Executiva: Construção de histograma (com curva KDE), boxplot geral e boxplot comparativo por grupo para sustentar a recomendação de triagem inteligente e roteamento especializado.

🛠️ Tecnologias Utilizadas
Linguagem: Python 3

Ambiente: Google Colab

Manipulação e Análise de Dados: pandas, numpy

Integração e Dados Sintéticos: gspread, faker

Visualização de Dados: matplotlib, seaborn

👩‍💻 Autora
Cristina Satie Vatanabe

Engenheira de Produção | Pós-graduanda em Análise Estratégica de Dados
