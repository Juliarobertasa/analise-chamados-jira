# Fontes e Arquitetura de Dados

## 1. Fontes de Dados

No MVP, os dados são exportados diretamente do Jira por meio de planilhas CSV. Nas próximas versões, será implementada uma integração via API, permitindo a atualização automática e em tempo real dos dados, eliminando a necessidade de exportações manuais. 

**Diagrama simplificado do fluxo de dados:**  

---

## 2. Modelagem e Relacionamentos

Descreva o modelo de dados (Esquema Estrela ou Floco de Neve) e as principais tabelas.  

**Exemplo:** Modelo de Esquema Estrela  

| Tipo      | Nome da Tabela       | Descrição                                      |
|-----------|-------------------|-----------------------------------------------|
| Fato      | FT - Chamados           | Contém dados dos chamados, tempos, status e outras informações relevantes   |
| Fato      | FT - Área relacionadas  | Informações de áreas (Front-end, Back-end, Produto)               |
| Dimensão  | DIM - Calendar Resolução             | Tempo de resolução de cada chamado     |


**Relacionamentos:**  
- FT - Chamados → DIM - Calendar Resolução (N:1)  
- FT - Chamados → FT - Área relacionadas (1:N)  

---

## 3. Medidas e Cálculos (DAX)

As principais medidas e fórmulas DAX utilizadas no dashboard foram: 

**Exemplos:**  

| Métrica           | Medidas e Cálculos | Descrição  |                                    
|-------------------|----------------------------------------------------------|----------------------------------------------------------|
| Tempo de Resolução (HH:MM:SS)     | `VAR hours = ROUNDDOWN([tempo de resolucao]/ 3600, 0) \ VAR minutes = ROUNDDOWN(MOD([tempo de resolucao], 3600) / 60, 0) \ VAR seconds = INT(MOD([tempo de resolucao], 60))` |Converte o tempo de resolução em segundos para o formato legível `HH:MM:SS`  |
| **Semana do Mês**              | `"Semana " & 1 + WEEKNUM('DIM - Calendar Resolucao'[Date]) - WEEKNUM(STARTOFMONTH('DIM - Calendar Resolucao'[Date]))` | Identifica a semana do mês para cada data, facilitando análises temporais. |
| **Chamados**                   | `COUNTROWS('FT - Chamados')` | Conta o total de registros (linhas) na tabela de fatos de chamados. |
| **Total de Chamados**          | `DISTINCTCOUNT('FT - Chamados'[Chave do chamado])` | Conta o número de chamados distintos, evitando duplicidades. |
| **Tempo de Resolução**        | `DATEDIFF('FT - Chamados'[Criado], 'FT - Chamados'[Resolvido], SECOND)` | Calcula o tempo total de resolução dos chamados em segundos. |
| **Tempo Médio de Resolução**  | `AVERAGE('FT - Chamados'[Tempo de resolucao])` | Retorna o tempo médio de resolução dos chamados. |
| **Total de Clientes**         | `DISTINCTCOUNT('FT - Chamados'[Associação])` | Conta o número de clientes únicos associados aos chamados. |
| **Chamados por Área**         | `COUNTROWS('FT - Areas realacionadas')` | Conta o total de chamados registrados por área responsável. |
| **DIM - Calendar Resolucao**  | | Criação de calendário dinâmico com base nas datas de resolução, permitindo análises por período. | 

