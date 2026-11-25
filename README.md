
# Projeto de Tratamento de Dados e Conformidade com a LGPD 🛡️📊

Este projeto demonstra uma pipeline completa de engenharia e preparação de dados utilizando **Python** e **Pandas**. O objetivo principal é consolidar bases de dados distintas de clientes, benefícios de saúde e compras corporativas, aplicando boas práticas de tratamento e regras de privacidade em conformidade com a **LGPD (Lei Geral de Proteção de Dados)**.

## 📌 Funcionalidades do Projeto

- **Integração de Múltiplas Fontes (Data Merge):** Consolidação de dados relacionais utilizando chaves estrangeiras (`cpf` e `cliente_id`) em etapas lógicas.
- **Conformidade com a LGPD:** 
  - Remoção de colunas com dados sensíveis que não eram estritamente necessários para as análises de negócios.
  - **Mascaramento de Dados de Localização:** Anonimização parcial do CEP, mantendo apenas a informação de macrorregião (três primeiros dígitos) para preservar a privacidade do usuário.
- **Engenharia de Recursos (Feature Engineering):** Agrupamento da idade em faixas etárias padronizadas (`18-25`, `26-35`, `36-50`, `50+`) utilizando a função `pd.cut` para facilitar análises demográficas sem expor a idade exata individual.

## 🛠️ Tecnologias Utilizadas

- **Python 3.x**
- **Pandas** (para manipulação e análise de dados)
- **Jupyter Notebook / Google Colab**

## 📂 Estrutura dos Arquivos de Entrada

O projeto consome três bases de dados principais em formato `.csv`:
1. `clientes.csv`: Contém dados cadastrais básicos como CPF, nome, idade e CEP.
2. `beneficios_saude.csv`: Informações de planos de saúde e condições crônicas associadas ao CPF.
3. `compras.csv`: Histórico de transações financeiras, valores gastos e categorias de produtos indexados por ID de cliente.

## 🚀 Como Executar o Projeto

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
Certifique-se de que os arquivos clientes.csv, beneficios_saude.csv e compras.csv estejam no mesmo diretório ou configurados no caminho correto.
Abra o notebook Jupyter e execute as células em sequência.
📈 Resultados Obtidos
Ao final do processamento, a tabela anonimizada pronta para o consumo por times de Analytics e BI apresenta a seguinte estrutura:

cliente_id: Identificador único anonimizado.
plano_saude / condicao_cronica: Variáveis de saúde integradas.
valor_gasto / categoria: Dados transacionais.
regiao: CEP mascarado (ex: 123xx-xxx).
faixa_etaria: Classificação etária protegendo o dado bruto.
