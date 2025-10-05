# Documentação de Negócio

## Contexto e Problema de Negócio

Atualmente, o registro dos chamados oriundos do Jira é realizado de forma manual no Notion. Cada chamado precisa ser inserido individualmente.

A partir desse registro, são feitas análises como:

- Quantidade total de chamados;
- Tipos de solicitações mais recorrentes;
- Áreas com maior volume de demandas;
- Comparativo entre chamados concluídos e cancelados.

### Cenário atual
- Registro manual dos chamados  
- Alta incidência de erros  
- Falta de visibilidade e controle dos dados 

## Principais problemas

Dos problemas identificados no processo atual de registro e análise de chamados, destacam-se os seguintes pontos:

- Consumo excessivo de tempo no registro dos chamados.
- Processo lento e suscetível a erros, por ser realizado manualmente.
- Falta de precisão e confiabilidade nos dados utilizados para análise.
- Limitação nas análises disponíveis, restringindo a visão estratégica.
- Dificuldade na tomada de decisão, devido à baixa qualidade e atraso das informações.
 

## Objetivo estratégico

Dos objetivos gerais, destacam-se:

- Reduzir o esforço manual, eliminando etapas repetitivas e suscetíveis a erros.
- Redirecionar o tempo investido em registros para atividades mais estratégicas.
- Aumentar a confiabilidade das informações, garantindo maior precisão nos dados.
- Relacionar diferentes informações, possibilitando análises mais aprofundadas.
- Reduzir o tempo de tratamento dos chamados, agilizando a resposta ao cliente.
- Identificar chamados críticos, priorizando atendimentos de maior impacto.
- Melhorar o acompanhamento das tratativas em tempo real, aumentando a transparência.
- Identificar gargalos e gerar insights, contribuindo para a melhoria contínua do produto.
  
---

## Metodologia de Análise

Para o desenvolvimento deste projeto, foram aplicadas metodologias de Business Intelligence (BI) e de metodologia ágil (Agile). O ciclo de BI incluiu ETL, modelagem de dados e criação de dashboards, garantindo que os dados fossem transformados em informações confiáveis e acionáveis. A abordagem ágil permitiu iterações rápida e ajustes incrementais, assegurando que o dashboard atendesse às necessidades do negócio de forma eficiente.

1. **ETL (Extração, Transformação e Carga)**
   - **Extração:** coletar dados do Jira (via exportação CSV).
   - **Transformação:** tratar e padronizar os dados, corrigindo inconsistências, duplicidades e formatos divergentes.
   - **Carga:** consolidar os dados tratados em arquivo CSV exportadas do Jira, organizadas e estruturadas para análise no Power BI.

2. **Modelagem de Dados**
   - Criar um **modelo de dados eficiente** para suportar análises rápidas e precisas.
   - Definir **tabelas Fato** (ex.: Chamados) e **Dimensões** (ex.: Tempo, CS Team, Prioridade) com relacionamentos claros.

3. **Desenvolvimento de Métricas e Dashboards**
   - Construir medidas e cálculos DAX, como Tempo Médio de Tratamento.
   - Criar dashboards interativos com filtros, gráficos e tabelas, facilitando o acompanhamento.

4. **Iteração e Melhoria Contínua**
   - Aplicar metodologia ágil, implementando melhorias incrementalmente.
   - Incorporar novas fontes de dados, métricas e análises conforme evolução das necessidades do negócio.
