# Requisitos Não-Funcionais (RNF)

## Visão Geral

Os Requisitos Não-Funcionais definem as características de qualidade, performance, segurança e usabilidade do sistema de Biblioteca Escolar. Estes requisitos devem ser considerados em todas as histórias de usuário e validados como parte da Definition of Done.

---

## 📊 Requisitos Não-Funcionais por Categoria

### 1. **PERFORMANCE**

| ID | Requisito | Descrição | Métrica |
|-------|-----------|-----------|---------|
| RNF-01 | Tempo de Resposta | O sistema deve responder a requisições em tempo máximo de 2 segundos | ≤ 2s por requisição |
| RNF-02 | Pesquisa de Livros | A pesquisa de livros deve retornar resultados em menos de 1 segundo | ≤ 1s |
| RNF-03 | Carregamento de Página | Páginas devem carregar completamente em até 3 segundos | ≤ 3s |
| RNF-04 | Concurrent Users | O sistema deve suportar 50+ usuários simultâneos | ≥ 50 conexões |
| RNF-05 | Cache | Implementar cache para consultas frequentes | - |

---

### 2. **SEGURANÇA**

| ID | Requisito | Descrição | Critério |
|-------|-----------|-----------|---------|
| RNF-06 | Autenticação | Autenticação obrigatória com login e senha | ✓ Login requerido |
| RNF-07 | Senha | Senhas devem ter mínimo 8 caracteres | Min 8 chars |
| RNF-08 | Criptografia | Dados sensíveis devem ser armazenados criptografados | ✓ Encrypted |
| RNF-09 | HTTPS | Todas as comunicações devem usar HTTPS | ✓ SSL/TLS |
| RNF-10 | Controle de Acesso | Diferentes níveis de acesso por papel (Aluno, Bibliotecário) | ✓ RBAC |
| RNF-11 | Injeção SQL | Proteção contra SQL Injection e XSS | ✓ Validação |
| RNF-12 | Auditoria | Registrar logs de acesso e operações críticas | ✓ Logging |

---

### 3. **USABILIDADE**

| ID | Requisito | Descrição | Critério |
|-------|-----------|-----------|---------|
| RNF-13 | Interface Intuitiva | Interface amigável para usuários de 8 a 18 anos | ✓ Testes com usuários |
| RNF-14 | Responsividade | Interface deve funcionar em desktop, tablet e celular | ✓ Mobile-first |
| RNF-15 | Acessibilidade | Suportar WCAG 2.1 nível AA | ✓ Contrast ratio ≥ 4.5:1 |
| RNF-16 | Navegação | Menu e navegação claros com máximo 3 cliques | ✓ User Testing |
| RNF-17 | Feedback | Sistema deve fornecer feedback claro ao usuário | ✓ Mensagens de status |
| RNF-18 | Idioma | Sistema disponível em Português Brasileiro | ✓ PT-BR |

---

### 4. **DISPONIBILIDADE E CONFIABILIDADE**

| ID | Requisito | Descrição | Métrica |
|-------|-----------|-----------|---------|
| RNF-19 | Uptime | Sistema deve estar disponível 99.5% do tempo | ≥ 99.5% |
| RNF-20 | Horário de Funcionamento | Disponível nos horários escolares (7h às 18h) | 7h-18h |
| RNF-21 | Backup | Realizar backups diários dos dados | ✓ Daily |
| RNF-22 | Recuperação | RTO (Recovery Time Objective) ≤ 4 horas | ≤ 4h |
| RNF-23 | Tratamento de Erros | Erros devem ser tratados com mensagens claras | ✓ User-friendly |

---

### 5. **COMPATIBILIDADE**

| ID | Requisito | Descrição | Navegadores |
|-------|-----------|-----------|---------|
| RNF-24 | Compatibilidade | Suportar os navegadores mais utilizados | Chrome, Firefox, Safari, Edge |
| RNF-25 | Versão Mínima | Suportar 2 versões anteriores de cada navegador | N-2 |
| RNF-26 | Sistema Operacional | Funcionar em Windows, macOS e Linux | ✓ Todos |

---

### 6. **ESCALABILIDADE**

| ID | Requisito | Descrição | Critério |
|-------|-----------|-----------|---------|
| RNF-27 | Crescimento de Dados | Arquitetura preparada para crescimento de até 5x | ✓ Escalável |
| RNF-28 | Banco de Dados | Índices e queries otimizadas para performance | ✓ Indexação |
| RNF-29 | Modularidade | Sistema modular para fácil manutenção e expansão | ✓ Microserviços |

---

### 7. **MANUTENIBILIDADE**

| ID | Requisito | Descrição | Critério |
|-------|-----------|-----------|---------|
| RNF-30 | Documentação | Código bem documentado e documentação técnica | ✓ README + Comments |
| RNF-31 | Versionamento | Usar controle de versão (Git) | ✓ GitHub |
| RNF-32 | Testes | Cobertura mínima de 80% de testes automatizados | ≥ 80% |
| RNF-33 | CI/CD | Pipeline de integração e deploy contínuo | ✓ Implementado |

---

## 📋 Mapeamento para Definition of Done (DoD)

Os requisitos não-funcionais devem ser validados antes de considerar uma história como concluída:

### Checklist de DoD Atualizado:
- [ ] A funcionalidade estiver implementada
- [ ] Todos os critérios de aceitação forem atendidos
- [ ] Os testes forem executados com sucesso
- [ ] Não existirem erros críticos
- [ ] O código estiver revisado
- [ ] A documentação estiver atualizada
- [ ] A interface estiver validada pelo Product Owner
- **[NOVO]** ✅ Requisitos não-funcionais aplicáveis foram atendidos (performance, segurança, usabilidade)
- **[NOVO]** ✅ Testes de segurança executados (injeção SQL, XSS, autenticação)
- **[NOVO]** ✅ Interface responsiva testada em desktop, tablet e mobile

---

## 🎯 Prioridade de Implementação

### Sprint 1 (MVP)
- ✅ **Crítica:** RNF-06 (Autenticação), RNF-07 (Senha), RNF-14 (Responsividade)
- ✅ **Alta:** RNF-01 (Performance), RNF-13 (Interface Intuitiva), RNF-17 (Feedback)

### Incrementos Futuros
- ⏳ **Média:** RNF-15 (Acessibilidade), RNF-32 (Testes Automatizados), RNF-04 (Concurrent Users)
- ⏳ **Baixa:** RNF-33 (CI/CD), RNF-29 (Microserviços), RNF-27 (Escalabilidade avançada)

---

## 📖 Referências

- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [ISO/IEC 9126 - Software Quality Characteristics](https://en.wikipedia.org/wiki/ISO/IEC_9126)

---

**Documento gerado:** 08/06/2026  
**Versão:** 1.0  
**Autora:** Luciana Coda Sant Anna Gomes
