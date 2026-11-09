# Análise Exploratória de Dados do Varejo (AED)
Curso: Análise de Dados com Python  
Turma: T7
Aluna: Letícia Perin Kolling  
Ferramentas Utilizadas: Python, Pandas, Google Colab, Git/GitHub.

## Visão Geral do Projeto

Este projeto consiste em uma Análise Exploratória de Dados (AED) aplicada a uma base de dados do varejo (`Base_Varejo.csv`). O objetivo principal é realizar o processo de limpeza e tratamento dos dados (ETL), extrair estatísticas descritivas sobre o perfil dos clientes e gerar agrupamentos estratégicos para responder a perguntas de negócio, como as vendas por categoria e segmentação de clientes.

## Base de Dados

https://www.kaggle.com/datasets/namespaiva/base-varejo/data  

## Como Executar no Google Colab

**Abrir o Notebook:** Faça upload do arquivo `.ipynb` para o seu Google Drive ou abra-o diretamente no Google Colab.
**Carregar a Base de Dados:** Certifique-se de que o arquivo `Base_Varejo.csv` está disponível na pasta do seu Google Drive ou faça o upload direto do arquivo no menu lateral de arquivos do Colab (`/content/Base_Varejo.csv`).
**Ajustar o Caminho:** Se necessário, atualize o caminho do arquivo no comando `pd.read\_csv()` na célula de carregamento inicial.
**Executar o Script:**
Clique no menu superior em Ambiente de execução (Runtime).
Selecione a opção Executar tudo (Run all) ou use o atalho `Ctrl + F9`.

## Reflexão Teórica: ETL e Qualidade de Dados

Na análise de dados real, dados brutos raramente vêm prontos para consumo. O processo de ETL (Extract, Transform, Load) garante que dados de fontes diversas sejam padronizados e validados antes de servirem para tomadas de decisão ou dashboards.
Durante este mini-projeto, foram observados aspectos cruciais de Qualidade dos Dados:

**Completude:** A base continha colunas totalmente sem preenchimento (`Unnamed: 10` a `13`), além de valores codificados como `#N/D`. A remoção e o imputamento planejado garantiram a integridade dos cálculos.

**Unicidade (Duplicidade):** Foram identificadas 96.553 linhas totalmente duplicadas. A remoção foi essencial para evitar a contagem dupla de vendas e a distorção dos volumes transacionados.

**Consistência de Tipos:** A coluna de datas veio como string (`object`) e foi devidamente convertida para o tipo `datetime64`, permitindo validações temporais adequadas.

