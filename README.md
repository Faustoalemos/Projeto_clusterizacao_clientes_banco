# Clusterizacao de Clientes para Direcionamento de Vendas no Financiamento Automotivo

Este projeto aplica inteligencia de dados e Machine Learning seguindo a metodologia rigorosa do CRISP-DM para resolver um desafio real de negocios no setor de financiamento de veiculos no Brasil: a falta de personalizacao nas campanhas de marketing, que gerava dispersao de margem e esforco de vendas ineficiente.

O objetivo principal foi identificar perfis de consumo e comportamento de credito para desenhar acoes comerciais de alta conversao (Cross-Selling e Up-Selling), com foco no retorno financeiro (ROI) para a companhia.

## 🚀 Como este Projeto Gera Valor de Negocio?

Em vez de aplicar filtros manuais e cegos em planilhas, o modelo de Machine Learning cruzou variaveis de Renda, Score de Credito, Tiquete de Contrato e Satisfacao de forma multidimensional. 

Simulamos a aplicacao do modelo em uma campanha de venda de Seguro Auto com um cupom de incentivo de 100 Reais. Os resultados demonstram o impacto direto na ultima linha do balanco financeiro:

- **Abordagem Tradicional Massiva (Sem Modelo):** Disparo generico para toda a base. O custo de pulverizacao engoliu a margem, gerando um **PREJUIZO LIQUIDO de 18.357,40 Reais**.
- **Abordagem Inteligente (Com K-Means):** Filtro cirurgico focado no Cluster ideal de compradores. A assertividade fez a conversao saltar para 15 por cento, entregando um **LUCRO LIQUIDO POSITIVO de 37.752,12 Reais**.

**Impacto Financeiro Real:** O modelo reverteu a operacao deficitaria e **INJETOU UM GANHO MONETARIO REAL INCREMENTAL DE 56.109,52 Reais** na companhia com uma unica acao comercial.

---

## 📋 Dicionario de Dados (Metadados)

A base de dados conta com 5.000 registros de clientes ativos estruturados in 10 colunas:

- **id_cliente:** Identificador unico e exclusivo do cliente.
- **idade:** Idade do cliente em anos completos.
- **genero:** Genero registrado (Feminino / Masculino).
- **estado_civil:** Estado civil declarado do cliente.
- **renda_mensal:** Renda liquida mensal comprovada ou estimada em Reais.
- **score_credito:** Pontuacao no biro de credito, variando de 200 a 1000.
- **produto_automotivo_digital:** Principal produto ou servico automotivo ativo.
- **valor_contrato_compra:** Valor monetario total do contrato ativo em Reais.
- **frequencia_interacao_6m:** Quantidade de acessos nos canais digitais nos ultimos 6 meses.
- **satisfacao:** Nota atribuida pelo cliente ao servico (CSAT), de 1 a 10.

---

## 🛠️ Tecnologias e Metodologia Utilizadas

O projeto foi inteiramente desenvolvido em Python dentro do ecossistema Anaconda Jupyter, utilizando as seguintes ferramentas:

- **Metodologia:** CRISP-DM (Business Understanding, Data Understanding, Data Prep, Modeling, Evaluation, Deployment).
- **Processamento de Dados:** Pandas e NumPy.
- **Visualizacao Grafica:** Seaborn e Matplotlib (Graficos univariados, bivariados, Boxplots e correlacao).
- **Machine Learning:** Scikit-Learn (Algoritmo K-Means, StandardScaler para normalizacao e One-Hot Encoding para variaveis de texto).
- **Validacao Estatistica:** Metodo do Cotovelo (Inercia WCSS) e Analise do Silhouette Score apontando em conjunto para o numero ideal de 4 clusters.
- **Salvamento do Modelo:** Joblib para serializacao em producao.

---

## 🎯 As 4 Personas Encontradas e as Acoes de Marketing

1. **Cluster 0: Compradores Core (Financiamento CDC)**
   - Perfil: Clientes com contratos de alto tiquete (media de 95.817,51 Reais) focados na compra do bem fisico.
   - Estrategia: Disparar oferta automatizada de Seguro e Tag no exato momento da assinatura, aumentando o Tempo de Vida do Cliente (LTV) de forma organica.

2. **Cluster 1: Clientes Protegidos (Seguro Auto)**
   - Perfil: Clientes com contratos de tiquete medio (3.665,90 Reais) e alto indice de fidelidade.
   - Estrategia: Oferecer campanhas de Emprestimo com Garantia de Veiculo com taxas reduzidas apos 6 meses de carteira.

3. **Cluster 2: Usuarios de Conveniencia (Tag de Pedagio)**
   - Perfil: Alta frequencia de uso no aplicativo, mas baixo tiquete gasto (998,46 Reais).
   - Estrategia: Direcionar exclusivamente os cupons de desconto para incentivar o upgrade de relacionamento para financiamento de carros.

4. **Cluster 3: Tomadores de Credito (Garantia de Veiculo)**
   - Perfil: Clientes em busca de liquidez financeira rapida usando o carro como lastro (media de 48.124,32 Reais).
   - Estrategia: Oferta de Seguro Auto embutido nas parcelas para mitigar o risco de inadimplencia e proteger o colateral.

---

## 📈 Roadmap para Producao (Deployment)

Para garantir a autonomia do time de Planejamento e Marketing, o modelo foi desenhado para rodar de forma automatizada no banco de dados corporativo:

1. **Fase 1:** O modelo e o padronizador sao salvos em arquivos fisicos (`.pkl`) via Joblib.
2. **Fase 2:** Um script em Python agendado no Apache Airflow roda toda madrugada processando os novos clientes cadastrados.
3. **Fase 3:** Os resultados alimentam a tabela analitica `tb_clusterizacao_clientes_marketing` dentro da Data Warehouse (SQL).
4. **Fase 4:** Os analistas de marketing extraem as listas de cupons rodando queries SQL simples ou baixando a base direto de um painel de Power BI, sem encostar em linhas de codigo Python.

