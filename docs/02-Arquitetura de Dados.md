# Fontes e Arquitetura de Dados

## 1. Fontes de Dados

De onde vieram os dados e como eles se conectam.  

**Exemplo:**  
> Extração do sistema Jira via API ou exportação CSV.  

**Observações:**  
- Garantir atualização periódica das fontes  
- Validar integridade dos dados antes da carga  

**Diagrama simplificado do fluxo de dados:**  

---

## 2. Modelagem e Relacionamentos

Descreva o modelo de dados (Esquema Estrela ou Floco de Neve) e as principais tabelas.  

**Exemplo:** Modelo de Esquema Estrela  

| Tipo      | Nome da Tabela       | Descrição                                      |
|-----------|-------------------|-----------------------------------------------|
| Fato      | Chamados           | Contém dados dos chamados, tempos e status    |
| Dimensão  | Tempo              | Informações de datas e períodos               |
| Dimensão  | CS Team            | Informações sobre os membros da equipe CS     |
| Dimensão  | Prioridade         | Classificação dos chamados por prioridade     |

**Relacionamentos principais:**  
- Chamados → Tempo (1:N)  
- Chamados → CS Team (1:N)  
- Chamados → Prioridade (1:N)

---

## 3. Medidas e Cálculos (DAX)

Apresente as fórmulas DAX mais importantes ou complexas utilizadas no dashboard.  

**Exemplos:**  

| Métrica           | Fórmula DAX                                               | Descrição                                      |
|------------------|----------------------------------------------------------|-----------------------------------------------|
| Média de CSAT     | `CALCULATE(AVERAGE('CS'[Nota]), 'CS'[Status] = "Fechado")` | Calcula a nota média dos chamados fechados    |
| Tempo Médio       | `AVERAGE('Chamados'[TempoTratamento])`                  | Calcula o tempo médio de tratamento dos chamados |
| Chamados Abertos  | `COUNTROWS(FILTER('Chamados', 'Chamados'[Status]="Aberto"))` | Contagem de chamados ainda abertos           |

> Observação: sempre documentar o propósito de cada medida para facilitar manutenção e ajustes futuros.

