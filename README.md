# 🛠️ Pipeline de Engenharia de Dados: Unificação ENEM (2009–2021)

## 📖 Descrição do Módulo
Este repositório é dedicado à etapa de **ETL (Extract, Transform, Load)** do projeto de análise histórica do ENEM. O desafio central foi consolidar 12 anos de microdados em um único dataset coeso, superando as frequentes mudanças estruturais nos arquivos disponibilizados pelo INEP.

## 🚀 Desafios Técnicos & Soluções Implementadas

1. **Gestão de Memória e Performance**

Dada a natureza de **Big Data** dos microdados do ENEM (milhões de registros por ano), o script foi otimizado para:
    
  - **Carga Seletiva**: Uso do parâmetro usecols para importar apenas as variáveis essenciais para a análise (UF, Notas, Redação, Língua Estrangeira, etc.), reduzindo drasticamente o consumo de memória RAM.
    
  - **Filtros Prematuros**: Limpeza de registros de candidatos ausentes ou eliminados durante o processo de leitura, garantindo um dataframe final mais leve e focado.

2. **Padronização de Esquema (Schema Mapping)**

Entre 2009 e 2021, o INEP alterou diversas vezes as nomenclaturas das colunas. O script resolve isso através de:

- **Dicionários de Mapeamento**: Criação de estruturas de mapeamento específicas para cada ciclo de anos, garantindo a integridade dos dados após a concatenação.

- **Injeção de Metadados**: Adição dinâmica da coluna `ANO` para permitir análises de séries temporais após a união das bases.

3. **Tratamento de Enconding**

Resolução de conflitos de codificação entre diferentes anos (alternando entre `ISO-8859-1` e `UTF-8`) para evitar erros de leitura e perda de caracteres especiais.

## 📁 Estrutura do Repositório

- `junta_dataset.ipynb`: Notebook com a lógica de pré-processamento, limpeza e unificação.

- `microdados_enem_09_21.csv`: (Output) Arquivo consolidado pronto para análise (Devido ao tamanho, o arquivo deve ser gerado localmente).

## 🛠️ Tecnologias

- **Linguagem**: Python

- **Biblioteca**: Pandas

## 📺 Explicação Técnica no YouTube

O processo de construção deste código e a lógica por trás da unificação estão documentados aqui:

- 🔗 [Vídeo: Junção dos Datasets de 2009 a 2021](https://www.youtube.com/watch?v=v4_rztci45s)

## 👤 Autor

Alan Vieira - *Engenheiro de Telecomunicações & Especialista em Dados*

- [LinkedIn](https://www.linkedin.com/in/alansilvavieira)

- [GitHub Portfólio](https://github.com/alan-vieira)
