# 🎯 ESTRATÉGIA DE PRODUTO: Roadmap + Backlog Integrados

## Contexto

A Lean Inception (Miro) identificou **13 features** no total para o sistema de biblioteca escolar. O desafio é **organizar e sequenciar** essas features de forma estratégica para entregar valor incremental respeitando:

- ✅ Dependências técnicas e lógicas
- ✅ Risco e complexidade
- ✅ Valor de negócio
- ✅ Capacidade do time

---

## Parte 1: ESTRUTURA LÓGICA - Os 3 Épicos

Para organizar as 13 features de forma escalável, decidiu-se agrupar por **domínio de negócio** em 3 Épicos:

### **Epic BK-9: Gestão de Usuários** (2 stories)

**Features:**
- BK-1: Cadastro e Consulta de Alunos (Sprint 1)
- BK-4: Login (Sprint 1)
- BK-17: Gerenciamento de Acessos (Sprint 5)

**Por quê juntos?**
- Todos lidam com **usuários e autenticação**
- Relacionados a permissões e controle de acesso
- Base para todas as outras features

**Valor de negócio:** Essencial para segurança

---

### **Epic BK-10: Gestão de Livros** (6 stories)

**Features:**
- BK-2: Cadastro e Consulta de Livros (Sprint 1)
- BK-5: Pesquisar Livros (Sprint 1)
- BK-6: Visualizar Disponibilidade (Sprint 1)
- BK-12: Editar Livros (Sprint 3)
- BK-13: Avaliar Livros (Sprint 3)
- BK-16: Relatórios e Estatísticas (Sprint 5)

**Por quê juntos?**
- Todas sobre **gerenciamento do acervo**
- Core da biblioteca escolar
- Mesma contexto de domínio

**Valor de negócio:** Descoberta, engajamento e decisões estratégicas

---

### **Epic BK-11: Gestão de Empréstimos** (5 stories)

**Features:**
- BK-3: Registrar Empréstimos e Devoluções (Sprint 2)
- BK-7: Reservar Livro (Sprint 2)
- BK-14: Avisos de Atraso (Sprint 4)
- BK-15: Avisos de Retorno (Sprint 4)

**Por quê juntos?**
- Todas sobre o **ciclo de empréstimo**
- Núcleo operacional da biblioteca
- Fluxo: Empréstimo → Prazo → Devolução

**Valor de negócio:** Operação principal, reduz perda de livros

---

## Parte 2: SEQUÊNCIA TEMPORAL - Os 5 Incrementos

Após análise de **risco, complexidade, dependências e valor de negócio**, as 13 features foram distribuídas em **5 sprints** (~10 semanas):

```
Semana 1-2    │ Semana 3-4    │ Semana 5-6    │ Semana 7-8    │ Semana 9-10
──────────────┼───────────────┼───────────────┼───────────────┼─────────────
  Sprint 1    │   Sprint 2    │   Sprint 3    │   Sprint 4    │  Sprint 5
  (5 stories) │  (2 stories)  │  (2 stories)  │  (2 stories)  │ (2 stories)
  21 pts      │   13 pts      │   10 pts      │   13 pts      │  16 pts
              │               │               │               │
MVP: Catálogo │ MVP: Completo │ Edição/Avali. │Notificações   │Relatórios
```

---

### **INCREMENTO 1: MVP - Alicerce do Catálogo** (Sprint 1 - 21 pts)

**Objetivo:** Validar estrutura de catálogo antes de adicionar empréstimos

**Features:**
1. **BK-1: Cadastro e Consulta de Alunos** (5 pts) - Epic: BK-9
2. **BK-4: Login** (3 pts) - Epic: BK-9
3. **BK-2: Cadastro e Consulta de Livros** (5 pts) - Epic: BK-10
4. **BK-5: Pesquisar Livros** (5 pts) - Epic: BK-10
5. **BK-6: Visualizar Disponibilidade** (3 pts) - Epic: BK-10

**Justificativa:**
- ✅ **Reduz risco:** Valida infraestrutura antes de lógica complexa
- ✅ **Entrega valor:** Alunos podem explorar acervo
- ✅ **Independente:** Nenhuma depende de empréstimos
- ✅ **Manageable:** 21 pts é volume adequado para 2 semanas

**Risco:** Baixo
**Complexidade:** Baixa

---

### **INCREMENTO 2: MVP - Gestão de Empréstimos** (Sprint 2 - 13 pts)

**Objetivo:** Implementar ciclo completo de empréstimos (MVP conforme Miro)

**Features:**
1. **BK-3: Registrar Empréstimos e Devoluções** (8 pts) - Epic: BK-11
2. **BK-7: Reservar Livro** (5 pts) - Epic: BK-11

**Justificativa:**
- ✅ **MVP Completo:** Agora temos os 4 pilares do Miro
- ✅ **Sequência lógica:** Depende de Sprint 1 estar pronto
- ✅ **Moderado:** 13 pts é volume realista
- ✅ **Core business:** Implementação do negócio principal

**Risco:** Médio
**Complexidade:** Alta
**Marcos:** 🎉 MVP Completo (pronto para validação com usuários)

---

### **INCREMENTO 3: Melhorias no Catálogo** (Sprint 3 - 10 pts)

**Objetivo:** Permitir que bibliotecários mantenham catálogo e alunos avaliem livros

**Features:**
1. **BK-12: Editar Livros** (5 pts) - Epic: BK-10
2. **BK-13: Avaliar Livros** (5 pts) - Epic: BK-10

**Justificativa:**
- ✅ **Depende de:** Sprint 1 + 2 (MVP estável)
- ✅ **Complexidade moderada:** Formulários + validações
- ✅ **Valor:** Manutenção + engajamento
- ⚠️ **Não-crítico:** MVP funciona sem isso

**Risco:** Baixo
**Complexidade:** Média

---

### **INCREMENTO 4: Sistema de Notificações** (Sprint 4 - 13 pts)

**Objetivo:** Notificar alunos e bibliotecários sobre prazos críticos

**Features:**
1. **BK-14: Avisos de Atraso** (8 pts) - Epic: BK-11
2. **BK-15: Avisos de Retorno** (5 pts) - Epic: BK-11

**Justificativa:**
- ✅ **Depende de:** Sprint 2 (empréstimos devem estar prontos)
- ✅ **Complexidade alta:** Integração com email/SMS + agendamento
- ✅ **Impacto operacional:** Essencial para escala
- ✅ **Pode ser MVP 2:** Biblioteca consegue operar sem isso por um tempo

**Risco:** Médio
**Complexidade:** Alta
**Tecnologia:** Sistema de fila (Celery/RabbitMQ), Email (SendGrid/AWS SES), Cron jobs

---

### **INCREMENTO 5: Analytics e Administração** (Sprint 5 - 16 pts)

**Objetivo:** Fornecer insights sobre uso + controle total de acessos

**Features:**
1. **BK-16: Relatórios e Estatísticas** (8 pts) - Epic: BK-10
2. **BK-17: Gerenciamento de Acessos** (8 pts) - Epic: BK-9

**Justificativa:**
- ✅ **Depende de:** Todos os incrementos anteriores
- ✅ **Complexidade alta:** Agregações + dashboards
- ✅ **Impacto estratégico:** Suporta decisões de negócio
- ✅ **Escalabilidade:** Necessário em longo prazo

**Risco:** Médio
**Complexidade:** Alta
**Tecnologia:** BI/Analytics (Metabase/Grafana), Controle de acesso granular, Auditoria

---

## Parte 3: MATRIZ DE PRIORIZAÇÃO

| Feature | Risco | Complexidade | Valor MVP | Dependências | Prioridade | Sprint |
|---------|-------|--------------|-----------|--------------|-----------|--------|
| **BK-1** | ⬇️ Baixo | ⬇️ Baixa | 🔴 Crítico | Nenhuma | 🔥 P0 | Sprint 1 |
| **BK-4** | ⬇️ Baixo | ⬇️ Baixa | 🔴 Crítico | Nenhuma | 🔥 P0 | Sprint 1 |
| **BK-2** | ⬇️ Baixo | ⬇️ Baixa | 🔴 Crítico | Nenhuma | 🔥 P0 | Sprint 1 |
| **BK-5** | ⬇️ Baixo | ⬇️ Baixa | 🔴 Crítico | BK-1, BK-2 | 🔥 P0 | Sprint 1 |
| **BK-6** | ⬇️ Baixo | ⬇️ Baixa | 🔴 Crítico | BK-2 | 🔥 P0 | Sprint 1 |
| **BK-3** | ⬜ Médio | ⬆️ Alta | 🔴 Crítico | BK-1,2,5,6 | 🔥 P0 | Sprint 2 |
| **BK-7** | ⬇️ Baixo | ⬜ Média | 🔴 Crítico | BK-1,2,5,6 | 🔥 P0 | Sprint 2 |
| **BK-12** | ⬇️ Baixo | ⬜ Média | 🟠 Alto | BK-1,2,3 | ✅ P1 | Sprint 3 |
| **BK-13** | ⬇️ Baixo | ⬜ Média | 🟡 Médio | BK-2,5,6 | ✅ P2 | Sprint 3 |
| **BK-14** | ⬆️ Alto | ⬆️ Alta | 🟠 Alto | BK-3 | ⚠️ P1 | Sprint 4 |
| **BK-15** | ⬜ Médio | ⬜ Média | 🟠 Alto | BK-3 | ⚠️ P1 | Sprint 4 |
| **BK-16** | ⬜ Médio | ⬆️ Alta | 🟡 Médio | BK-2,3,5 | ✅ P2 | Sprint 5 |
| **BK-17** | ⬜ Médio | ⬆️ Alta | 🟠 Alto | Nenhuma | ⚠️ P1 | Sprint 5 |

---

## Parte 4: DECISÕES CHAVE

### **Por que essa ordem? (Resposta integrada)**

**Sprint 1 antes de Sprint 2:**
- ✅ **Risco reduzido:** Validar catálogo antes de empréstimos
- ✅ **Independência:** Nenhuma feature depende de empréstimos
- ✅ **Feedback cedo:** Colher feedback de usuários em 2 semanas

**Sprint 2 logo depois:**
- ✅ **MVP fica pronto:** Temos os 4 pilares do Miro
- ✅ **Sequência lógica:** Depende de Sprint 1
- ✅ **Validação:** Pronto para testar com usuários reais

**Sprint 3 depois (não urgente):**
- ✅ **MVP estável primeiro:** Consolidar features core
- ✅ **Manutenção operacional:** Bibliotecário consegue editar dados
- ✅ **Baixo risco:** Features isoladas

**Sprint 4 com dependência clara:**
- ✅ **Requer empréstimos:** Depende de BK-3 funcionando
- ✅ **Impacto alto:** Reduz perda de livros
- ✅ **Integração externa:** Email/SMS requer setup

**Sprint 5 por último:**
- ✅ **Acumula dados:** Relatórios precisam de histórico
- ✅ **Menos urgente:** Analytics é nice-to-have no início
- ✅ **Escalabilidade:** Essencial em produção

---

## Parte 5: ALTERNATIVAS CONSIDERADAS (E REJEITADAS)

### ❌ **Alternativa 1: Tudo em Sprint 1**
**Problema:** 34 story points em 2 semanas = impossível, alto risco

### ❌ **Alternativa 2: Empréstimos antes de Catálogo**
**Problema:** Não dá para testar empréstimos sem livros cadastrados

### ❌ **Alternativa 3: Organizar só por Risco**
**Problema:** Viola dependências, BK-14 depende de BK-3

### ✅ **Alternativa 4: Épicos + Sprints + Incrementos (ESCOLHIDA)**
**Vantagens:** Respeita dependências, entrega valor incremental, risco gerenciado, timeline realista

---

## Parte 6: RASTREABILIDADE (Miro → Jira)

### **Ferramentas Utilizadas:**

- **Miro:** [Acessar Board Lean Inception](https://miro.com/app/board/uXjVHL7MC3U=/?share_link_id=1464223721)
- **Jira Backlog:** [Acessar Backlog](https://lucianacoda.atlassian.net/jira/software/projects/BK/boards/67/backlog)
- **Jira Sprint:** [Acessar Board Sprint Atual](https://lucianacoda.atlassian.net/jira/software/projects/BK/boards/67)

### **Mapeamento de Features:**

| # | Feature | Issue | Epic | Sprint | Status |
|---|---------|-------|------|--------|--------|
| 1 | Cadastro Alunos | BK-1 | BK-9 | Sprint 1 | ✅ |
| 2 | Login | BK-4 | BK-9 | Sprint 1 | ✅ |
| 3 | Cadastro Livros | BK-2 | BK-10 | Sprint 1 | ✅ |
| 4 | Pesquisar Livros | BK-5 | BK-10 | Sprint 1 | ✅ |
| 5 | Disponibilidade | BK-6 | BK-10 | Sprint 1 | ✅ |
| 6 | Empréstimos | BK-3 | BK-11 | Sprint 2 | ✅ |
| 7 | Reservar | BK-7 | BK-11 | Sprint 2 | ✅ |
| 8 | Editar Livros | BK-12 | BK-10 | Sprint 3 | ⏳ |
| 9 | Avaliar Livros | BK-13 | BK-10 | Sprint 3 | ⏳ |
| 10 | Avisos Atraso | BK-14 | BK-11 | Sprint 4 | ⏳ |
| 11 | Avisos Retorno | BK-15 | BK-11 | Sprint 4 | ⏳ |
| 12 | Relatórios | BK-16 | BK-10 | Sprint 5 | ⏳ |
| 13 | Admin | BK-17 | BK-9 | Sprint 5 | ⏳ |

**Cobertura:** 100% (13/13 features mapeadas) ✅

---

## Parte 7: WORKFLOW NO JIRA

### **Estado Sprint 1-2: ATIVO**
```
Sprint 1 (5 stories)
├─ BK-1: Cadastro Alunos
├─ BK-4: Login
├─ BK-2: Cadastro Livros
├─ BK-5: Pesquisar Livros
└─ BK-6: Disponibilidade

Sprint 2 (2 stories)
├─ BK-3: Empréstimos
└─ BK-7: Reservar
```

### **Estado Sprint 3+: BACKLOG**
```
BACKLOG (não assignado a sprint)
├─ BK-12: Editar Livros [Labels: incremento-3, future-feature, sprint-3]
├─ BK-13: Avaliar Livros [Labels: incremento-3, future-feature, sprint-3]
├─ BK-14: Avisos Atraso [Labels: incremento-4, future-feature, sprint-4]
├─ BK-15: Avisos Retorno [Labels: incremento-4, future-feature, sprint-4]
├─ BK-16: Relatórios [Labels: incremento-5, future-feature, sprint-5]
└─ BK-17: Admin [Labels: incremento-5, future-feature, sprint-5]
```

### **Transição Sprint 2 → Sprint 3**
No planning: Mover BK-12, BK-13 do Backlog para Sprint 3

---

## Parte 8: TIMELINE RESUMIDA

| Sprint | Semanas | Features | Pts | Milestone |
|--------|---------|----------|-----|-----------|
| **1** | 1-2 | Catálogo | 21 | ✅ MVP: Básico |
| **2** | 3-4 | Empréstimos | 13 | 🎉 **MVP: Completo** |
| **3** | 5-6 | Edição/Avali. | 10 | ✨ Manutenção |
| **4** | 7-8 | Notificações | 13 | 📧 Operacional |
| **5** | 9-10 | Analytics | 16 | 📊 Estratégico |
| **TOTAL** | 10 | 13 features | 73 | ✅ Sistema Completo |

---

## Conclusão

Esta estratégia oferece:

1. ✅ **Estrutura clara** - 3 Épicos organizam por domínio
2. ✅ **Timeline realista** - MVP em Sprint 2, Sistema em Sprint 5
3. ✅ **Risco gerenciado** - Dependências respeitadas, progressão lógica
4. ✅ **Valor incremental** - Cada sprint entrega algo novo
5. ✅ **Escalabilidade** - Fácil adicionar features futuras
6. ✅ **Rastreabilidade** - 100% mapeado Miro → Jira

**MVP pronto para validação com usuários após Sprint 2.**  
**Sistema completo pronto para produção após Sprint 5.**

---

**Documento criado:** 08/06/2026  
**Responsáveis:** Product Owner, Scrum Master e Arquitetura
