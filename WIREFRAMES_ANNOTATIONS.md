# 📐 ANOTAÇÕES TÉCNICAS - Wireframes

**Detalhes de implementação, validações e estados para cada wireframe**

## 🔗 Acesso ao Figma

**Design de Alta Fidelidade e Prototipação:**
- [Acessar Figma - EduBook PUC](https://www.figma.com/design/4I51qHv63A3xZLQH2ZIkHm/EduBook-PUC)

---

## 1️⃣ Login.png (BK-4: US-04)

### **Fluxo**
```
[Tela vazia] → [Usuário entra credenciais] → [Clica Entrar] → [Validação] → [Dashboard ou Erro]
```

### **Campos e Validações**

**Campo: Usuário**
- Tipo: Text
- Placeholder: "Digite seu usuário"
- Validação:
  - Obrigatório
  - Mínimo 3 caracteres
  - Sem espaços em branco
- Mensagem de erro: "Usuário é obrigatório e deve ter mínimo 3 caracteres"

**Campo: Senha**
- Tipo: Password (ocultar caracteres)
- Placeholder: "Digite sua senha"
- Validação:
  - Obrigatório
  - Mínimo 8 caracteres
  - Armazenar como hash no BD
- Mensagem de erro: "Senha é obrigatória e deve ter mínimo 8 caracteres"

**Botão: Entrar**
- Tipo: Primary Button
- Ação: Validar credenciais
- Estados:
  - Normal: Clicável
  - Hover: Destacar visualmente
  - Loading: Mostrar spinner + "Validando..."
  - Disabled: Se campos vazios

### **Estados da Tela**

**Estado 1: Tela Inicial**
```
[Logo EduBook]
Usuário: [campo vazio]
Senha: [campo vazio]
[Botão Entrar - desabilitado]
```

**Estado 2: Preenchendo Dados**
```
[Logo EduBook]
Usuário: [usuário123 - digitado]
Senha: [••••••• - digitado]
[Botão Entrar - habilitado]
```

**Estado 3: Carregando**
```
[Logo EduBook]
Usuário: [usuário123]
Senha: [•••••••]
[⏳ Validando...] (botão desabilitado com spinner)
```

**Estado 4: Sucesso**
```
✅ Login realizado com sucesso!
Redirecionando para dashboard...
```

**Estado 5: Erro - Credenciais Inválidas**
```
[Logo EduBook]
❌ Usuário ou senha inválidos
Usuário: [usuário123]
Senha: [•••••••]
[Botão Entrar - habilitado]
```

**Estado 6: Erro - Campo Vazio**
```
[Logo EduBook]
⚠️ Usuário é obrigatório
Usuário: [vazio] - Bordura vermelha
Senha: [•••••••]
[Botão Entrar - desabilitado]
```

### **Critérios de Aceitação Técnicos**
- ✅ Campo usuário obrigatório, mín 3 caracteres
- ✅ Campo senha obrigatório, mín 8 caracteres
- ✅ Mensagem de erro clara para credenciais inválidas
- ✅ Redirecionar para dashboard após sucesso
- ✅ Loading indicator durante validação
- ✅ Botão desabilitado quando campos vazios

---

## 2️⃣ Cadastro de Alunos.png (BK-1: US-01)

### **Fluxo**
```
[Tela vazia] → [Preencher formulário] → [Validar] → [Salvar] → [Confirmação]
```

### **Campos e Validações**

**Campo: Matrícula**
- Tipo: Text
- Validação:
  - Obrigatório
  - Formato: [A-Z]{3}\d{6} (ex: ABC123456)
  - Deve ser única (não duplicar)
- Mensagem de erro: "Matrícula inválida ou já existe"

**Campo: Nome Completo**
- Tipo: Text
- Validação:
  - Obrigatório
  - Mínimo 3 caracteres
  - Máximo 100 caracteres
- Mensagem de erro: "Nome deve ter entre 3 e 100 caracteres"

**Campo: E-mail**
- Tipo: Email
- Validação:
  - Obrigatório
  - Formato válido de e-mail (regex)
  - Deve ser único
- Mensagem de erro: "E-mail inválido ou já cadastrado"

**Campo: Turma**
- Tipo: Select Dropdown
- Validação:
  - Obrigatório
  - Opções: 6º ano, 7º ano, 8º ano, 9º ano, 1º EM, 2º EM, 3º EM
- Mensagem de erro: "Turma é obrigatória"

**Botão: Salvar**
- Ação: Validar todos os campos
- Estados:
  - Normal: Clicável
  - Loading: "Salvando..."
  - Disabled: Se campos inválidos

### **Estados da Tela**

**Estado 1: Tela Inicial**
```
Cadastrar Alunos
Matrícula: [vazio]
Nome Completo: [vazio]
E-mail: [vazio]
Turma: [Selecione] (dropdown)
[Salvar - desabilitado]
```

**Estado 2: Preenchendo**
```
Cadastrar Alunos
Matrícula: [ABC123456 - verde ✓]
Nome Completo: [João Silva - verde ✓]
E-mail: [joao@email.com - verde ✓]
Turma: [9º ano ✓]
[Salvar - habilitado]
```

**Estado 3: Validação Erro**
```
Cadastrar Alunos
Matrícula: [ABC1234] ❌ Formato inválido
Nome Completo: [JJ] ❌ Mínimo 3 caracteres
E-mail: [joao@] ❌ E-mail inválido
Turma: [Selecione] ❌ Obrigatório
[Salvar - desabilitado]
```

**Estado 4: Salvando**
```
Cadastrar Alunos
[Todos os campos preenchidos]
[⏳ Salvando...] (botão desabilitado)
```

**Estado 5: Sucesso**
```
✅ Aluno cadastrado com sucesso!
Dados salvos no sistema.
[Fechar] ou [Novo cadastro]
```

**Estado 6: Erro ao Salvar**
```
❌ Erro ao salvar: Matrícula já existe
Verifique os dados e tente novamente.
[Salvar - habilitado para tentar novamente]
```

### **Critérios de Aceitação Técnicos**
- ✅ Matrícula: validação de formato + unicidade
- ✅ Nome: 3-100 caracteres
- ✅ E-mail: validação e unicidade
- ✅ Turma: obrigatória, select com opções
- ✅ Botão desabilitado se campos inválidos
- ✅ Feedback visual de validação (vermelho = erro, verde = ok)
- ✅ Mensagem de sucesso ao salvar

---

## 3️⃣ Cadastro de Livros.png (BK-2: US-02)

### **Fluxo**
```
[Tela vazia] → [Preencher] → [Validar] → [Salvar] → [Confirmação]
```

### **Campos e Validações**

**Campo: Título**
- Tipo: Text
- Validação:
  - Obrigatório
  - 3-200 caracteres
- Erro: "Título deve ter 3-200 caracteres"

**Campo: Autor**
- Tipo: Text
- Validação:
  - Obrigatório
  - 3-100 caracteres
- Erro: "Autor deve ter 3-100 caracteres"

**Campo: Quantidade**
- Tipo: Number
- Validação:
  - Obrigatório
  - Número positivo
  - Máximo 999 exemplares
- Erro: "Quantidade deve ser um número entre 1 e 999"

**Botão: Salvar**
- Ação: Validar e salvar no BD

### **Estados da Tela**

**Estado 1: Vazio**
```
Cadastrar Livros
Título: [vazio]
Autor: [vazio]
Quantidade: [vazio]
[Salvar - desabilitado]
```

**Estado 2: Preenchido**
```
Cadastrar Livros
Título: [Dom Casmurro ✓]
Autor: [Machado de Assis ✓]
Quantidade: [5 ✓]
[Salvar - habilitado]
```

**Estado 3: Sucesso**
```
✅ Livro cadastrado com sucesso!
"Dom Casmurro" por Machado de Assis (5 exemplares)
[Novo cadastro] [Ver catálogo]
```

### **Critérios de Aceitação Técnicos**
- ✅ Título: 3-200 caracteres
- ✅ Autor: 3-100 caracteres
- ✅ Quantidade: número 1-999
- ✅ Botão desabilitado se inválido
- ✅ Feedback visual de erro
- ✅ Confirmação de sucesso

---

## 4️⃣ Pesquisa de Livros.png (BK-5: US-05)

### **Fluxo**
```
[Campo vazio] → [Digitar termo] → [Buscar] → [Resultados]
```

### **Campo de Busca**
- Tipo: Text
- Placeholder: "Digite título do livro"
- Validação:
  - Mínimo 2 caracteres para buscar
  - Sem validação especial (aceita qualquer texto)
- Timeout: 1 segundo para buscar

### **Resultados**

**Estado 1: Inicial**
```
Pesquisar Livro
[Campo vazio]
[Buscar]

Resultados
(nenhum resultado ainda)
```

**Estado 2: Buscando**
```
Pesquisar Livro
[Dom]
[Buscar]

Resultados
⏳ Buscando...
```

**Estado 3: Com Resultados**
```
Pesquisar Livro
[Dom]
[Buscar]

Resultados (2 encontrados)
┌─────────────────────┐
│ Dom Casmurro        │
│ Autor: Machado Assis│
│ Disponível         │
└─────────────────────┘

┌─────────────────────┐
│ Dom Quixote         │
│ Autor: Cervantes    │
│ Disponível         │
└─────────────────────┘
```

**Estado 4: Sem Resultados**
```
Pesquisar Livro
[XYZ]
[Buscar]

Resultados
❌ Nenhum livro encontrado para "XYZ"
Tente com outro termo
```

**Estado 5: Resultado Único**
```
Pesquisar Livro
[Harry]
[Buscar]

Resultados (1 encontrado)
┌──────────────────────┐
│ Harry Potter         │
│ Autor: J.K. Rowling │
│ Disponível          │
└──────────────────────┘
```

### **Critérios de Aceitação Técnicos**
- ✅ Buscar por título
- ⚠️ Buscar por autor (adicionar segunda opção)
- ✅ Retorno em < 1 segundo
- ✅ Exibir resultados com título, autor, disponibilidade
- ✅ Mensagem "não encontrado" clara
- ✅ Mostrar quantidade de resultados

---

## 5️⃣ Disponibilidade do Livro.png (BK-6: US-06)

### **Fluxo**
```
[Clica em livro] → [Abre detalhes] → [Mostra disponibilidade] → [Pode reservar]
```

### **Campos de Detalhes**

**Informações do Livro:**
- Título: Texto estático
- Autor: Texto estático
- Disponibilidade: Dinâmico (atualiza após empréstimo)

**Indicadores de Disponibilidade:**

**Caso 1: Disponível**
```
Detalhes do Livro
┌────────────────┐
│ Título:        │
│ Dom Casmurro   │
│                │
│ Autor:         │
│ Machado Assis  │
│                │
│ Disponibilidade:
│ ✅ 3 Exemplares
└────────────────┘

[Reservar]
```

**Caso 2: Indisponível**
```
Detalhes do Livro
┌────────────────┐
│ Título:        │
│ Harry Potter   │
│                │
│ Autor:         │
│ J.K. Rowling   │
│                │
│ Disponibilidade:
│ ❌ Indisponível
│    Volta em 3 dias
└────────────────┘

[Alertar quando disponível]
```

**Caso 3: Apenas 1 Exemplar**
```
Detalhes do Livro
┌────────────────┐
│ Título:        │
│ 1984           │
│                │
│ Autor:         │
│ George Orwell  │
│                │
│ Disponibilidade:
│ ⚠️ 1 Exemplar restante
└────────────────┘

[Reservar] [Emprestar]
```

### **Botão: Reservar**
- Ação: Criar reserva para este aluno
- Estados:
  - Normal: Clicável se disponível
  - Disabled: Se indisponível
  - Loading: "Reservando..."
  - Success: "✅ Reservado com sucesso"

### **Critérios de Aceitação Técnicos**
- ✅ Exibir quantidade disponível
- ⚠️ Indicador visual claro para indisponível
- ✅ Botão Reservar habilitado se disponível
- ✅ Atualizar em tempo real após empréstimo
- ⚠️ Mostrar quando volta a estar disponível
- ✅ Feedback visual de ações

---

## 🎯 Resumo das Validações

| Wireframe | Campo Crítico | Validação | Mensagem Erro |
|-----------|---------------|-----------|---------------|
| Login | Senha | Min 8 chars | "Senha inválida" |
| Cadastro Alunos | Matrícula | Unique + Formato | "Matrícula existe/inválida" |
| Cadastro Livros | Quantidade | 1-999 número | "Número inválido" |
| Pesquisar | Termo | Min 2 chars | "Nenhum resultado" |
| Disponibilidade | Quantidade | Dinâmico | "Indisponível" |

---

## ✅ Checklist de Implementação

- [ ] Login: Validação + loading + erro
- [ ] Cadastro Alunos: Todos os campos validados
- [ ] Cadastro Livros: Quantidade numérica validada
- [ ] Pesquisa: Timeout 1s + "não encontrado"
- [ ] Disponibilidade: Indicador visual de indisponível
- [ ] Todos: Feedback visual (cores, ícones, mensagens)

---

**Tempo estimado para implementação:** 40-60 horas (considerando backend + frontend + testes)

**Prioridade:** Sprint 1 = Login, Cadastro Alunos, Cadastro Livros, Pesquisa, Disponibilidade
