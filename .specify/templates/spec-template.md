# Especificação da Funcionalidade: [NOME DA FUNCIONALIDADE]

**Ramo da funcionalidade**: `[###-feature-name]`

**Criado em**: [DATA]

**Status**: Rascunho

**Entrada**: Descrição do usuário: "$ARGUMENTS"

## Cenários de Usuário e Testes *(obrigatório)*

<!--
  IMPORTANTE: As histórias de usuário devem ser PRIORIZADAS como jornadas do usuário ordenadas por importância.
  Cada história/jornada de usuário deve ser TESTÁVEL DE FORMA INDEPENDENTE — ou seja, se você implementar apenas UMA delas,
  ainda assim deve existir um MVP (Produto Mínimo Viável) viável que entregue valor.

  Atribua prioridades (P1, P2, P3, etc.) a cada história, em que P1 é a mais crítica.
  Pense em cada história como uma fatia independente de funcionalidade que pode ser:
  - Desenvolvida independentemente
  - Testada independentemente
  - Implantada independentemente
  - Demonstrada aos usuários independentemente
-->

### História de Usuário 1 - [Título Breve] (Prioridade: P1)

[Descreva esta jornada do usuário em linguagem simples]

**Por que esta prioridade**: [Explique o valor e por que ela recebe este nível de prioridade]

**Teste Independente**: [Descreva como isso pode ser testado de forma independente - por exemplo, "Pode ser totalmente testado por [ação específica] e entrega [valor específico]"]

**Cenários de Aceitação**:

1. **Dado** [estado inicial], **Quando** [ação], **Então** [resultado esperado]
2. **Dado** [estado inicial], **Quando** [ação], **Então** [resultado esperado]

---

### História de Usuário 2 - [Título Breve] (Prioridade: P2)

[Descreva esta jornada do usuário em linguagem simples]

**Por que esta prioridade**: [Explique o valor e por que ela recebe este nível de prioridade]

**Teste Independente**: [Descreva como isso pode ser testado de forma independente]

**Cenários de Aceitação**:

1. **Dado** [estado inicial], **Quando** [ação], **Então** [resultado esperado]

---

### História de Usuário 3 - [Título Breve] (Prioridade: P3)

[Descreva esta jornada do usuário em linguagem simples]

**Por que esta prioridade**: [Explique o valor e por que ela recebe este nível de prioridade]

**Teste Independente**: [Descreva como isso pode ser testado de forma independente]

**Cenários de Aceitação**:

1. **Dado** [estado inicial], **Quando** [ação], **Então** [resultado esperado]

---

[Adicione mais histórias de usuário conforme necessário, cada uma com prioridade definida]

### Casos Limites

<!--
  AÇÃO NECESSÁRIA: O conteúdo desta seção representa placeholders.
  Preencha com os casos limites corretos.
-->

- O que acontece quando [condição de limite]?
- Como o sistema lida com [cenário de erro]?

## Requisitos *(obrigatório)*

<!--
  AÇÃO NECESSÁRIA: O conteúdo desta seção representa placeholders.
  Preencha com os requisitos funcionais corretos.
-->

### Requisitos Funcionais

- **RF-001**: O sistema DEVE [capacidade específica, por exemplo, "permitir que usuários criem contas"]
- **RF-002**: O sistema DEVE [capacidade específica, por exemplo, "validar endereços de e-mail"]
- **RF-003**: Os usuários DEVEM poder [interação principal, por exemplo, "redefinir sua senha"]
- **RF-004**: O sistema DEVE [requisito de dados, por exemplo, "persistir preferências do usuário"]
- **RF-005**: O sistema DEVE [comportamento, por exemplo, "registrar todos os eventos de segurança"]

*Exemplo de marcação para requisitos ainda não esclarecidos:*

- **RF-006**: O sistema DEVE autenticar usuários por meio de [NEEDS CLARIFICATION: método de autenticação não especificado — e-mail/senha, SSO, OAuth?]
- **RF-007**: O sistema DEVE reter dados do usuário por [NEEDS CLARIFICATION: período de retenção não especificado]

### Entidades-Chave *(inclua se a funcionalidade envolver dados)*

- **[Entidade 1]**: [O que ela representa, atributos-chave sem implementação]
- **[Entidade 2]**: [O que ela representa, relacionamentos com outras entidades]

## Critérios de Sucesso *(obrigatório)*

<!--
  AÇÃO NECESSÁRIA: Defina critérios de sucesso mensuráveis.
  Eles devem ser agnósticos em relação à tecnologia e mensuráveis.
-->

### Resultados Mensuráveis

- **CS-001**: [Métrica mensurável, por exemplo, "Os usuários conseguem concluir a criação de conta em menos de 2 minutos"]
- **CS-002**: [Métrica mensurável, por exemplo, "O sistema lida com 1000 usuários simultâneos sem degradação"]
- **CS-003**: [Métrica de satisfação do usuário, por exemplo, "90% dos usuários concluem a tarefa principal com sucesso na primeira tentativa"]
- **CS-004**: [Métrica de negócio, por exemplo, "Reduzir tickets de suporte relacionados a [X] em 50%"]

## Premissas

<!--
  AÇÃO NECESSÁRIA: Preencha com as premissas corretas com base em padrões razoáveis
  escolhidos quando a descrição da funcionalidade não especificou certos detalhes.
-->

- [Premissa sobre usuários-alvo, por exemplo, "Os usuários possuem conexão estável com a internet"]
- [Premissa sobre limites de escopo, por exemplo, "Suporte mobile está fora do escopo da v1"]
- [Premissa sobre dados/ambiente, por exemplo, "O sistema de autenticação existente será reutilizado"]
- [Dependência de sistema/serviço existente, por exemplo, "É necessário acesso à API existente de perfil do usuário"]
