# Clusterizacao de Clientes para Direcionamento de Vendas no Financiamento Automotivo

Este projeto aplica inteligencia de dados e Machine Learning seguindo a metodologia rigorosa do CRISP-DM para resolver um desafio real de negocios no setor de financiamento de veiculos no Brasil: a falta de personalizacao nas campanhas de marketing, que gerava dispersao de margem e esforco de vendas ineficiente.

O objetivo principal foi identificar perfis de consumo e comportamento de credito para desenhar acoes comerciais de alta conversao (Cross-Selling e Up-Selling), com foco no retorno financeiro (ROI) para a companhia.

---

### 📌 Sumario Executivo e Guia de Navegacao Rapida
- **1. Entendimento do Negocio** — O desafio comercial: como usar IA para acabar com panfletagem digital e focar em ofertas de alta conversao.
- **2. Analise Exploratoria dos Dados** — Raio-X de 10k registros revelando anomalias de cadastro, colisoes de strings e os primeiros padroes ocultos.
- **3. Preparacao e Limpeza dos Dados** — Engenharia de dados em acao: expurgo de ruidos, imputacao por mediana e codificacao binaria das variaveis.
- **4. Modelagem Estatistica com Machine Learning** — A matematica decide: validando a divisao ideal da base atraves do Metodo do Cotovelo e Silhouette Score.
- **5. Avaliacao de Personas e Perfilamento** — Traduzindo algoritmos em pessoas: o mapeamento demografico e comportamental das 5 novas personas.
- **6. Business Case e Retorno Financeiro (ROI)** — Dinheiro na mesa: a simulacao real que reverteu um prejuizo e injetou 65k de lucro liquido na operacao.
- **7. Roadmap de Producao e Implementacao** — Da teoria a pratica: a arquitetura automatizada (Airflow/SQL) para dar total autonomia ao time de marketing.

---

## 🚀 Como este Projeto Gera Valor de Negocio?

Em vez de aplicar filtros manuais e cegos em planilhas, o modelo de Machine Learning cruzou variaveis de Renda, Score de Credito, Tiquete de Contrato e Satisfacao de forma multidimensional. 

Simulamos a aplicacao do modelo em uma campanha de venda de Seguro Auto com um cupom de incentivo de 100 Reais. Os resultados demonstram o impacto direto na ultima linha do balanco financeiro:

- **Abordagem Tradicional Massiva (Sem Modelo):** Disparo generico para toda a base. O custo de pulverizacao engoliu a margem, gerando um **PREJUIZO LIQUIDO de 23.686,68 Reais**.
- **Abordagem Inteligente (Com K-Means):** Filtro cirurgico focado no Cluster ideal de compradores (Financiamento Varejo). A assertividade fez a conversao saltar para 15 por cento, entregando um **LUCRO LÍQUIDO POSITIVO de 41.713,72 Reais**.

**Impacto Financeiro Real:** O modelo reverteu a operacao deficitaria e **INJETOU UM GANHO MONETARIO REAL INCREMENTAL DE 65.400,40 Reais** na companhia com uma unica acao comercial.

---

## 📋 Dicionario de Dados (Metadados)

A base de dados conta com 10.000 registros de clientes ativos estruturados em 10 colunas:

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

## 🎯 As 5 Personas Encontradas e as Acoes de Marketing

1. **Cluster 0: Seguros Puros (Perfil Jovem Adulto / Entrada)**
   - Perfil: Clientes com contratos de baixo tiquete (media de 3.289,21 Reais) focados em protecao veicular.
   - Estrategia: Oferta de Credito com Garantia de Veiculo apos 6 meses de carteira ativa.

2. **Cluster 1: Financiamento Varejo (O Motor do Varejo Central)**
   - Perfil: Clientes com contratos de tiquete intermediario alto (media de 67.999,20 Reais). 
   - Estrategia: Campanha automatizada de Seguro e Tag no momento do fechamento (Público-alvo do nosso Business Case de sucesso).

3. **Cluster 2: Usuarios de Conveniencia (Tags Urbanas)**
   - Perfil: Publico mais jovem da base, com score em construcao e tiquete baixo (998,99 Reais).
   - Estrategia: Direcionar exclusivamente os cupons de incentivo para atrair o primeiro financiamento.

4. **Cluster 3: Tomadores de Credito (Garantia de Veiculo)**
   - Perfil: Clientes em busca de liquidez rapida usando o carro como lastro (media de 67.017,33 Reais).
   - Estrategia: Seguro embutido nas parcelas para mitigar o risco de inadimplencia e proteger o colateral.

5. **Cluster 4: Alta Renda / Premium (Os Clientes de Maior Valor)**
   - Perfil: Publico mais sênior, com altissimo score (media de 876) e contratos expressivos (media de 135.032,60 Reais).
   - Estrategia: Canal de atendimento exclusivo e cross-selling de produtos financeiros premium de alta margem.
