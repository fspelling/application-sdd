# Extensão de Contexto do Agente de Codificação

Esta extensão incorporada gerencia o **arquivo de contexto/instruções do agente de codificação** (por exemplo, `CLAUDE.md`, `.github/copilot-instructions.md`, `AGENTS.md`, `GEMINI.md`, …) para a integração ativa.

Ela gerencia o ciclo de vida da seção controlada delimitada pelos marcadores configuráveis de início/fim (padrões: `<!-- SPECKIT START -->` / `<!-- SPECKIT END -->`).

## Por que uma extensão?

Nem todos os usuários do Spec Kit desejam que o Spec Kit escreva no arquivo de contexto do agente de codificação. Extrair esse comportamento para uma extensão dedicada permite que os usuários:

- **Desativem completamente** com `specify extension disable agent-context` — o Spec Kit então nunca criará nem modificará o arquivo de contexto do agente.
- **Personalizem os marcadores** editando `.specify/extensions/agent-context/agent-context-config.yml` — tanto a camada Python quanto os scripts incorporados respeitam o mesmo valor `context_markers`.
- **Sincronizem múltiplos pontos de ancoragem** definindo `context_files` quando um projeto intencionalmente usa mais de um arquivo de contexto do agente, como `AGENTS.md` e `CLAUDE.md`.
- **Atualizem sob demanda** com `/speckit.agent-context.update`, ou automaticamente por meio dos hooks declarados em `extension.yml` (`after_specify`, `after_plan`).

## Comandos

| Comando | Descrição |
|---------|-------------|
| `speckit.agent-context.update` | Atualiza a seção gerenciada no arquivo de contexto do agente com o caminho atual do plano. |

## Configuração

Toda a configuração flui por meio do arquivo próprio da extensão em
`.specify/extensions/agent-context/agent-context-config.yml`:

```yaml
# Caminho para o arquivo de contexto do agente de codificação gerenciado por esta extensão
context_file: CLAUDE.md

# Lista opcional de arquivos de contexto do agente para gerenciar juntos.
# Quando não vazia, ela tem precedência sobre context_file.
context_files:
  - AGENTS.md
  - CLAUDE.md

# Delimitadores para a seção gerenciada do Spec Kit
context_markers:
  start: "<!-- SPECKIT START -->"
  end: "<!-- SPECKIT END -->"
```

- `context_file` — caminho relativo ao projeto para o arquivo de contexto do agente, escrito por `specify init` e `specify integration install`.
- `context_files` — caminhos relativos ao projeto para múltiplos arquivos de contexto do agente. Quando a lista não estiver vazia, ela tem precedência sobre `context_file`. Caminhos absolutos, separadores de barra invertida e segmentos `..` são rejeitados.
- `context_markers.start` / `.end` — os delimitadores ao redor da seção gerenciada. Edite estes para usar marcadores personalizados.

## Requisitos

Os scripts de atualização incorporados exigem **Python 3** com **PyYAML** para processamento YAML/upsert (o PowerShell também pode usar `ConvertFrom-Yaml`, quando disponível).

O PyYAML vem com a CLI `specify` e normalmente está disponível no mesmo interpretador `python3`. Se um hook relatar *"PyYAML is required … not available in the current Python environment"*, isso significa que o `python3` do sistema é diferente daquele usado para instalar o Spec Kit. Para resolver, execute:

```bash
pip install pyyaml
# ou alvos o interpretador específico usado pelo Spec Kit:
/path/to/speckit-python -m pip install pyyaml
```

## Desativar

```bash
specify extension disable agent-context
```

Quando desativada, o Spec Kit pula a criação, atualização e remoção do contexto do agente (os pontos de verificação estão dentro de `upsert_context_section()` e `remove_context_section()`).
Projetos desativados também ignoram valores antigos de `context_files` durante a renderização de comandos, então desativar a extensão permanece uma opção completa de opt-out.
