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

## Principais Conclusões e Insights do Projeto

**Concentração Massiva em Alimentos:** A categoria `ALIMENTOS` lidera isoladamente as vendas, representando 52,38% do volume total (384.197 transações).  
**Top 3 Categorias de Consumo:** `ALIMENTOS`, `HIGIENE` (18,77%) e `LIMPEZA` (17,54%) juntas somam 88,69% de todas as vendas da base.  
**Predominância do Segmento B:** No agrupamento por segmento de cliente (`CL_SEG`), o Segmento B é responsável por 63,88% (468.505 compras), seguido pelo Segmento C com 27,99% e Segmento A com apenas 8,14%.  
**Perfil Familiar (Número de Filhos - `CL_FHL`):** A média de filhos por cliente é de 1,14, porém a mediana e a moda são 0,00, indicando que a grande maioria dos clientes registrados não possui filhos cadastrados (75% da base tem até 2 filhos, com pico máximo em 4 filhos).  
**Tratamento de Anomalias de Cadastro:** Um total de 3.228 registros continha a flag de erro `#N/D` tanto no nome quanto na categoria do produto. Esses registros foram mantidos para preservação do volume transacional, mas reclassificados sob o rótulo `"SEM CATEGORIA"` e `"NÃO IDENTIFICADO"`.  

