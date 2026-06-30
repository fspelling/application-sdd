<!--
Sync Impact Report
- Version change: template placeholder → 1.0.0
- Modified principles: template placeholder → Especificação Antes da Implementação; template placeholder → Teste-Primeiro e Validação Independente; template placeholder → Incrementos MVP e Dependências Claras; template placeholder → Rastreabilidade e Documentação Viva; template placeholder → Simplicidade, Clareza e Manutenibilidade
- Added sections: Restrições Adicionais; Fluxo de Desenvolvimento
- Removed sections: None
- Templates requiring updates: ✅ [.specify/templates/plan-template.md](.specify/templates/plan-template.md); ✅ [.specify/templates/spec-template.md](.specify/templates/spec-template.md); ✅ [.specify/templates/tasks-template.md](.specify/templates/tasks-template.md)
- Follow-up TODOs: None
-->

# Constituição do application-sdd

## Princípios Fundamentais

### I. Especificação Antes da Implementação
Cada funcionalidade MUST começar com uma especificação concreta, contendo histórias de usuário priorizadas, cenários de aceitação, premissas e critérios de sucesso antes de qualquer código ou tarefa de implementação. Quando uma necessidade não estiver clara, a equipe MUST registrar o ponto de esclarecimento e evitar decisões implícitas.

### II. Teste-Primeiro e Validação Independente
Cada história de usuário MUST ter testes relevantes definidos antes da implementação, com foco em validar a jornada de forma independente. A implementação NÃO é considerada concluída até que os testes pertinentes tenham sido executados com sucesso e o comportamento esperado esteja demonstrado.

### III. Incrementos MVP e Dependências Claras
O trabalho MUST ser entregue em fatias testáveis e independentemente demonstráveis, com uma base mínima que bloqueie apenas o necessário. Dependências entre histórias devem ser explícitas, pequenas e documentadas para preservar a capacidade de entregar um MVP funcional.

### IV. Rastreabilidade e Documentação Viva
Spec, plan, tasks e implementação MUST permanecer sincronizados durante o ciclo de vida da funcionalidade. Qualquer mudança de escopo, decisão técnica ou requisito MUST atualizar os artefatos relevantes, sem deixar placeholders residuais em documentos finais.

### V. Simplicidade, Clareza e Manutenibilidade
A solução escolhida MUST ser a mais simples que atenda aos requisitos e preserve a clareza do código e da documentação. Abstrações desnecessárias, duplicações e decisões complexas sem justificativa válida são rejeitadas em favor de uma implementação direta e mantível.

## Restrições Adicionais

- Nenhuma alteração de código ou configuração MUST ser feita sem uma especificação, plano ou tarefa que justifique o trabalho.
- Regras de segurança e segredos MUST permanecer fora do repositório; credenciais e tokens NÃO devem ser versionados.
- Mudanças que alterem contratos, interfaces públicas ou comportamento esperado MUST manter a documentação atualizada.
- Revisões de PR MUST verificar conformidade com esta constituição antes da aprovação.

## Fluxo de Desenvolvimento

- O fluxo de trabalho MUST iniciar com a especificação da funcionalidade, seguida de planejamento e, quando necessário, pesquisa técnica.
- A verificação da constituição MUST ocorrer antes da fase de pesquisa e novamente após o design, conforme o template de plano.
- Tarefas de implementação MUST refletir as prioridades da especificação e os critérios de independência das histórias de usuário.
- A validação final MUST incluir testes relevantes, revisão dos artefatos impactados e checagem de consistência entre spec, plan e tasks.

## Governança

Esta constituição prevalece sobre práticas locais e serve como padrão obrigatório para mudanças no projeto. Qualquer alteração em princípios, seções ou regras de governança MUST incluir documentação do motivo, impacto esperado, versão semântica apropriada e revisão de conformidade antes da aprovação.

As mudanças menores que apenas clarifiquem texto podem usar PATCH; adições de princípio ou seção exigem MINOR; remoções ou redefinições incompatíveis exigem MAJOR. O histórico de mudanças MUST manter data e justificativa de cada revisão.

**Versão**: 1.0.0 | **Ratificada em**: 2026-06-30 | **Última alteração em**: 2026-06-30
