---

description: "Template de lista de tarefas para implementação de funcionalidades"
---

# Tarefas: [NOME DA FUNCIONALIDADE]

**Entrada**: Documentos de design em `/specs/[###-feature-name]/`

**Pré-requisitos**: plan.md (obrigatório), spec.md (obrigatório para histórias de usuário), research.md, data-model.md, contracts/

**Testes**: Os exemplos abaixo incluem tarefas de teste. Os testes são OPCIONAIS — somente inclua-os se forem explicitamente solicitados na especificação da funcionalidade.

**Organização**: As tarefas são agrupadas por história de usuário para permitir implementação e testes independentes de cada história.

## Formato: `[ID] [P?] [Story] Descrição`

- **[P]**: Pode ser executada em paralelo (arquivos diferentes, sem dependências)
- **[Story]**: A qual história de usuário esta tarefa pertence (por exemplo, US1, US2, US3)
- Inclua caminhos exatos de arquivos nas descrições

## Convenções de Caminho

- **Projeto único**: `src/`, `tests/` na raiz do repositório
- **Aplicação web**: `backend/src/`, `frontend/src/`
- **Mobile**: `api/src/`, `ios/src/` ou `android/src/`
- Os caminhos mostrados abaixo assumem um projeto único — ajuste com base na estrutura do plan.md

<!--
  ============================================================================
  IMPORTANTE: As tarefas abaixo são EXEMPLOS apenas para fins ilustrativos.

  O comando /speckit-tasks DEVE substituí-las por tarefas reais com base em:
  - Histórias de usuário de spec.md (com suas prioridades P1, P2, P3...)
  - Requisitos da funcionalidade de plan.md
  - Entidades de data-model.md
  - Endpoints de contracts/

  As tarefas DEVEM ser organizadas por história de usuário para que cada história possa ser:
  - Implementada independentemente
  - Testada independentemente
  - Entregue como incremento MVP

  NÃO mantenha essas tarefas de exemplo no arquivo generated tasks.md.
  ============================================================================
-->

## Fase 1: Configuração (Infraestrutura Compartilhada)

**Objetivo**: Inicialização do projeto e estrutura básica

- [ ] T001 Criar a estrutura do projeto conforme o plano de implementação
- [ ] T002 Inicializar o projeto [language] com dependências de [framework]
- [ ] T003 [P] Configurar ferramentas de linting e formatação

---

## Fase 2: Base (Pré-requisitos Bloqueantes)

**Objetivo**: Infraestrutura principal que DEVE estar concluída antes de qualquer história de usuário ser implementada

**⚠️ CRÍTICO**: Nenhum trabalho de história de usuário pode começar até esta fase ser concluída

Exemplos de tarefas de base (ajuste conforme seu projeto):

- [ ] T004 Configurar schema do banco de dados e framework de migrações
- [ ] T005 [P] Implementar framework de autenticação/autorização
- [ ] T006 [P] Configurar estrutura de roteamento e middleware da API
- [ ] T007 Criar modelos/entidades base dos quais todas as histórias dependem
- [ ] T008 Configurar infraestrutura de tratamento de erros e logging
- [ ] T009 Configurar gerenciamento de configuração de ambiente

**Ponto de verificação**: A base está pronta — a implementação das histórias de usuário pode agora começar em paralelo

---

## Fase 3: História de Usuário 1 - [Título] (Prioridade: P1) 🎯 MVP

**Objetivo**: [Descrição breve do que esta história entrega]

**Teste Independente**: [Como verificar que esta história funciona por conta própria]

### Testes para a História de Usuário 1 (OPCIONAL — somente se os testes forem solicitados) ⚠️

> **OBSERVAÇÃO: Escreva estes testes PRIMEIRO, garanta que ELES FALHEM antes da implementação**

- [ ] T010 [P] [US1] Teste de contrato para [endpoint] em tests/contract/test_[name].py
- [ ] T011 [P] [US1] Teste de integração para [jornada do usuário] em tests/integration/test_[name].py

### Implementação para a História de Usuário 1

- [ ] T012 [P] [US1] Criar modelo [Entity1] em src/models/[entity1].py
- [ ] T013 [P] [US1] Criar modelo [Entity2] em src/models/[entity2].py
- [ ] T014 [US1] Implementar [Service] em src/services/[service].py (depende de T012, T013)
- [ ] T015 [US1] Implementar [endpoint/funcionalidade] em src/[location]/[file].py
- [ ] T016 [US1] Adicionar validação e tratamento de erros
- [ ] T017 [US1] Adicionar logging para operações da história de usuário 1

**Ponto de verificação**: Neste ponto, a História de Usuário 1 deve estar totalmente funcional e testável de forma independente

---

## Fase 4: História de Usuário 2 - [Título] (Prioridade: P2)

**Objetivo**: [Descrição breve do que esta história entrega]

**Teste Independente**: [Como verificar que esta história funciona por conta própria]

### Testes para a História de Usuário 2 (OPCIONAL — somente se os testes forem solicitados) ⚠️

- [ ] T018 [P] [US2] Teste de contrato para [endpoint] em tests/contract/test_[name].py
- [ ] T019 [P] [US2] Teste de integração para [jornada do usuário] em tests/integration/test_[name].py

### Implementação para a História de Usuário 2

- [ ] T020 [P] [US2] Criar modelo [Entity] em src/models/[entity].py
- [ ] T021 [US2] Implementar [Service] em src/services/[service].py
- [ ] T022 [US2] Implementar [endpoint/funcionalidade] em src/[location]/[file].py
- [ ] T023 [US2] Integrar com os componentes da História de Usuário 1 (se necessário)

**Ponto de verificação**: Neste ponto, as Histórias de Usuário 1 e 2 devem funcionar independentemente

---

## Fase 5: História de Usuário 3 - [Título] (Prioridade: P3)

**Objetivo**: [Descrição breve do que esta história entrega]

**Teste Independente**: [Como verificar que esta história funciona por conta própria]

### Testes para a História de Usuário 3 (OPCIONAL — somente se os testes forem solicitados) ⚠️

- [ ] T024 [P] [US3] Teste de contrato para [endpoint] em tests/contract/test_[name].py
- [ ] T025 [P] [US3] Teste de integração para [jornada do usuário] em tests/integration/test_[name].py

### Implementação para a História de Usuário 3

- [ ] T026 [P] [US3] Criar modelo [Entity] em src/models/[entity].py
- [ ] T027 [US3] Implementar [Service] em src/services/[service].py
- [ ] T028 [US3] Implementar [endpoint/funcionalidade] em src/[location]/[file].py

**Ponto de verificação**: Todas as histórias de usuário devem agora ser funcionalmente independentes

---

[Adicione mais fases de histórias de usuário conforme necessário, seguindo o mesmo padrão]

---

## Fase N: Polimento e Preocupações Transversais

**Objetivo**: Melhorias que afetam várias histórias de usuário

- [ ] TXXX [P] Atualizações de documentação em docs/
- [ ] TXXX Limpeza de código e refatoração
- [ ] TXXX Otimização de performance em todas as histórias
- [ ] TXXX [P] Testes unitários adicionais (se solicitados) em tests/unit/
- [ ] TXXX Hardening de segurança
- [ ] TXXX Executar validação de quickstart.md

---

## Dependências e Ordem de Execução

### Dependências das Fases

- **Configuração (Fase 1)**: Sem dependências — pode começar imediatamente
- **Base (Fase 2)**: Depende da conclusão da Configuração — BLOQUEIA todas as histórias de usuário
- **Histórias de Usuário (Fase 3+)**: Todas dependem da conclusão da Fase Base
  - As histórias de usuário podem então prosseguir em paralelo (se houver capacidade)
  - Ou sequencialmente em ordem de prioridade (P1 → P2 → P3)
- **Polimento (Fase Final)**: Depende de todas as histórias de usuário desejadas estarem concluídas

### Dependências das Histórias de Usuário

- **História de Usuário 1 (P1)**: Pode começar após a Base (Fase 2) — sem dependências em outras histórias
- **História de Usuário 2 (P2)**: Pode começar após a Base (Fase 2) — pode integrar com US1, mas deve ser testável independentemente
- **História de Usuário 3 (P3)**: Pode começar após a Base (Fase 2) — pode integrar com US1/US2, mas deve ser testável independentemente

### Dentro de Cada História de Usuário

- Os testes (se incluídos) DEVEM ser escritos e FALHAREM antes da implementação
- Modelos antes de serviços
- Serviços antes de endpoints
- Implementação principal antes da integração
- História concluída antes de avançar para a próxima prioridade

### Oportunidades de Paralelismo

- Todas as tarefas de Configuração marcadas com [P] podem rodar em paralelo
- Todas as tarefas de Base marcadas com [P] podem rodar em paralelo (dentro da Fase 2)
- Uma vez concluída a fase de Base, todas as histórias de usuário podem começar em paralelo (se houver capacidade da equipe)
- Todos os testes de uma história de usuário marcados com [P] podem rodar em paralelo
- Modelos dentro de uma história marcados com [P] podem rodar em paralelo
- Diferentes histórias de usuário podem ser trabalhadas em paralelo por diferentes membros da equipe

---

## Exemplo de Paralelismo: História de Usuário 1

```bash
# Iniciar todos os testes da História de Usuário 1 juntos (se os testes forem solicitados):
Task: "Teste de contrato para [endpoint] em tests/contract/test_[name].py"
Task: "Teste de integração para [jornada do usuário] em tests/integration/test_[name].py"

# Iniciar todos os modelos da História de Usuário 1 juntos:
Task: "Criar modelo [Entity1] em src/models/[entity1].py"
Task: "Criar modelo [Entity2] em src/models/[entity2].py"
```

---

## Estratégia de Implementação

### MVP Primeiro (Somente História de Usuário 1)

1. Concluir a Fase 1: Configuração
2. Concluir a Fase 2: Base (CRÍTICO — bloqueia todas as histórias)
3. Concluir a Fase 3: História de Usuário 1
4. **PARAR E VALIDAR**: Testar a História de Usuário 1 de forma independente
5. Implantar/apresentar se estiver pronto

### Entrega Incremental

1. Concluir Configuração + Base → Base pronta
2. Adicionar História de Usuário 1 → Testar de forma independente → Implantar/Apresentar (MVP!)
3. Adicionar História de Usuário 2 → Testar de forma independente → Implantar/Apresentar
4. Adicionar História de Usuário 3 → Testar de forma independente → Implantar/Apresentar
5. Cada história agrega valor sem quebrar as anteriores

### Estratégia de Equipe Paralela

Com múltiplos desenvolvedores:

1. A equipe conclui Configuração + Base juntos
2. Quando a Base estiver concluída:
   - Desenvolvedor A: História de Usuário 1
   - Desenvolvedor B: História de Usuário 2
   - Desenvolvedor C: História de Usuário 3
3. As histórias são concluídas e integradas de forma independente

---

## Observações

- Tarefas [P] = arquivos diferentes, sem dependências
- Rótulo [Story] mapeia a tarefa para uma história específica para rastreabilidade
- Cada história de usuário deve ser concluída e testável de forma independente
- Verifique se os testes falham antes de implementar
- Faça commit após cada tarefa ou grupo lógico
- Pare em qualquer ponto de verificação para validar a história de forma independente
- Evite: tarefas vagas, conflitos no mesmo arquivo, dependências entre histórias que quebram a independência
