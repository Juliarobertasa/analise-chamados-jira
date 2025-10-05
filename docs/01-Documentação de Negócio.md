# Documentação de Negócio

## Contexto e Problema de Negócio

O ponto de partida: descreva o cenário atual e o objetivo estratégico do projeto.

**Dor identificada:**  
> Consumo de tempo e erros na consolidação de chamados de CS.

**Cenário atual:**  
- Registro manual dos chamados  
- Alta incidência de erros  
- Falta de visibilidade e controle dos dados  

**Objetivo estratégico:**  
Reduzir o esforço manual e aumentar a confiabilidade das informações.

---

## Objetivos e KPIs Chave

Quais perguntas o Dashboard precisa responder? Liste as métricas que guiarão a análise (os KPIs).

**Exemplos de objetivos e KPIs:**  

| Objetivo                            | KPI/Métrica                      |
|------------------------------------|---------------------------------|
| Reduzir o tempo médio de tratamento | Tempo Médio de Tratamento (TMT) |
| Identificar chamados críticos       | Número de chamados por prioridade|
| Melhorar a visibilidade             | Dashboard atualizado diariamente |

> Observação: métricas podem ser implementadas em DAX no Power BI.

---

## Metodologia de Análise

O seu "Plano de Ataque": descreva a abordagem usada para ir do problema à solução.

**Abordagem sugerida:**  
1. **ETL (Extração, Transformação e Carga)**  
   - Consolidar dados de todas as fontes  
2. **Modelagem Estrela**  
   - Criar tabelas fato e dimensão para análise eficiente  
3. **Validação com usuários-chave**  
   - Ajustar métricas e dashboards conforme feedback  

> A metodologia pode ser aplicada em ciclos ágeis, criando um MVP do dashboard e evoluindo conforme o uso.
