# Plano de Implementação: [FUNCIONALIDADE]

**Ramo**: `[###-feature-name]` | **Data**: [DATA] | **Especificação**: [link]

**Entrada**: Especificação da funcionalidade em `/specs/[###-feature-name]/spec.md`

**Observação**: Este template é preenchido pelo comando `/speckit-plan`. Consulte `.specify/templates/plan-template.md` para o fluxo de execução.

## Resumo

[Extrair da especificação da funcionalidade: requisito principal + abordagem técnica derivada da pesquisa]

## Contexto Técnico

<!--
  AÇÃO NECESSÁRIA: Substitua o conteúdo desta seção pelos detalhes técnicos
  do projeto. A estrutura aqui é apresentada como orientação para guiar o processo de iteração.
-->

**Linguagem/Versão**: [por exemplo, Python 3.11, Swift 5.9, Rust 1.75 ou NEEDS CLARIFICATION]

**Dependências Principais**: [por exemplo, FastAPI, UIKit, LLVM ou NEEDS CLARIFICATION]

**Armazenamento**: [quando aplicável, por exemplo, PostgreSQL, CoreData, arquivos ou N/A]

**Testes**: [por exemplo, pytest, XCTest, cargo test ou NEEDS CLARIFICATION]

**Plataforma Alvo**: [por exemplo, servidor Linux, iOS 15+, WASM ou NEEDS CLARIFICATION]

**Tipo de Projeto**: [por exemplo, biblioteca/cli/web-service/aplicativo-mobile/compiler/aplicativo-desktop ou NEEDS CLARIFICATION]

**Metas de Desempenho**: [específicas do domínio, por exemplo, 1000 req/s, 10k linhas/s, 60 fps ou NEEDS CLARIFICATION]

**Restrições**: [específicas do domínio, por exemplo, <200ms p95, <100MB de memória, offline-capable ou NEEDS CLARIFICATION]

**Escala/Abordagem**: [específicas do domínio, por exemplo, 10k usuários, 1M LOC, 50 telas ou NEEDS CLARIFICATION]

## Verificação da Constituição

*GATE: Deve passar antes da pesquisa da Fase 0. Reavaliar após o design da Fase 1.*

[Gates determinados com base no arquivo da constituição]

## Estrutura do Projeto

### Documentação (esta funcionalidade)

```text
specs/[###-feature]/
├── plan.md              # Este arquivo (saída do comando /speckit-plan)
├── research.md          # Saída da Fase 0 (comando /speckit-plan)
├── data-model.md        # Saída da Fase 1 (comando /speckit-plan)
├── quickstart.md        # Saída da Fase 1 (comando /speckit-plan)
├── contracts/           # Saída da Fase 1 (comando /speckit-plan)
└── tasks.md             # Saída da Fase 2 (comando /speckit-tasks - NÃO criado pelo /speckit-plan)
```

### Código-Fonte (raiz do repositório)
<!--
  AÇÃO NECESSÁRIA: Substitua a árvore de placeholders abaixo pela estrutura concreta
  desta funcionalidade. Remova as opções não utilizadas e expanda a estrutura escolhida com
  caminhos reais (por exemplo, apps/admin, packages/something). O plano entregue não deve
  incluir rótulos de opções.
-->

```text
# [REMOVA SE NÃO FOR USAR] Opção 1: Projeto único (PADRÃO)
src/
├── models/
├── services/
├── cli/
└── lib/

tests/
├── contract/
├── integration/
└── unit/

# [REMOVA SE NÃO FOR USAR] Opção 2: Aplicação web (quando "frontend" + "backend" forem detectados)
backend/
├── src/
│   ├── models/
│   ├── services/
│   └── api/
└── tests/

frontend/
├── src/
│   ├── components/
│   ├── pages/
│   └── services/
└── tests/

# [REMOVA SE NÃO FOR USAR] Opção 3: Mobile + API (quando "iOS/Android" forem detectados)
api/
└── [mesmo que backend acima]

ios/ ou android/
└── [estrutura específica da plataforma: módulos de funcionalidade, fluxos de UI, testes da plataforma]
```

**Decisão de Estrutura**: [Documente a estrutura selecionada e faça referência aos
diretórios reais capturados acima]

## Rastreamento de Complexidade

> **Preencha SOMENTE se a Verificação da Constituição tiver violações que precisem ser justificadas**

| Violação | Por que é necessária | Alternativa Mais Simples Rejeitada Porque |
|-----------|----------------------|-------------------------------------------|
| [por exemplo, 4º projeto] | [necessidade atual] | [por que 3 projetos são insuficientes] |
| [por exemplo, padrão do repositório] | [problema específico] | [por que o acesso direto ao banco não é suficiente] |
