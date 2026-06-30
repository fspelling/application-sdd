# Especificação da Funcionalidade: Catálogo de Livros API

**Ramo da funcionalidade**: `001-book-catalog-api`

**Criado em**: 2026-06-30

**Status**: Rascunho

**Entrada**: Descrição do usuário: "Criar um aplicativo (API REST), que terá como responsabilidade gerenciar um catálogo de livros, autores e categorias, possibilitando consultas e manutenção desses dados, onde as consultas serão feitas por usuários e o gerenciamento dos dados em si será realizado pelo administrador do sistema."

## Cenários de Usuário e Testes *(obrigatório)*

### História de Usuário 1 - Consulta do catálogo de livros (Prioridade: P1)

Um usuário pode pesquisar livros por título, autor, categoria ou termo livre para localizar rapidamente obras do catálogo.

**Por que esta prioridade**: Essa jornada entrega o valor principal do sistema, permitindo que usuários consultem o catálogo sem necessidade de manutenção administrativa.

**Teste Independente**: Pode ser totalmente testado por uma busca com filtros e entrega uma lista relevante de livros para o usuário.

**Cenários de Aceitação**:

1. **Dado** que o catálogo contém livros com diferentes títulos, autores e categorias, **Quando** um usuário realiza uma busca por título, **Então** o sistema retorna apenas os livros que correspondem ao termo informado.
2. **Dado** que existem livros associados a várias categorias, **Quando** um usuário filtra por categoria, **Então** o sistema retorna todos os livros daquela categoria em ordem de relevância ou identificação.
3. **Dado** que um usuário acessa um livro específico, **Quando** a consulta for realizada com um identificador válido, **Então** o sistema retorna os dados completos do livro, incluindo autores e categorias associados.

---

### História de Usuário 2 - Manutenção de categorias e autores (Prioridade: P2)

O administrador do sistema pode criar, atualizar, consultar e remover categorias e autores para manter o catálogo organizado.

**Por que esta prioridade**: Essa função garante a qualidade dos metadados do catálogo e suporta a manutenção dos relacionamentos usados nas consultas.

**Teste Independente**: Pode ser totalmente testado por operações administrativas de cadastro e atualização que alteram a disponibilidade dos registros no catálogo.

**Cenários de Aceitação**:

1. **Dado** que o administrador está autenticado no sistema, **Quando** ele cria uma nova categoria, **Então** a categoria fica disponível para associação a livros em consultas futuras.
2. **Dado** que uma categoria existe no sistema, **Quando** o administrador altera o nome ou a descrição, **Então** a alteração é persistida e refletida nas consultas subsequentes.
3. **Dado** que um autor existe no sistema, **Quando** o administrador remove o autor, **Então** o sistema impede a exclusão caso o autor ainda esteja associado a livros ativos, ou realiza a exclusão apenas após a remoção das dependências necessárias.

---

### História de Usuário 3 - Manutenção de livros (Prioridade: P1)

O administrador do sistema pode cadastrar, editar e remover livros, vinculando-os a autores e categorias corretas.

**Por que esta prioridade**: O gerenciamento de livros é o núcleo do catálogo e precisa estar disponível para sustentar as consultas dos usuários.

**Teste Independente**: Pode ser totalmente testado por operações de cadastro e atualização de livros com validações de integridade.

**Cenários de Aceitação**:

1. **Dado** que o administrador está autenticado, **Quando** ele cadastra um novo livro com título, autor(es) e categoria(s), **Então** o livro passa a estar disponível para consulta pública.
2. **Dado** que um livro já existe, **Quando** o administrador atualiza seus dados, **Então** as alterações são persistidas e aparecem nas consultas subsequentes.
3. **Dado** que um livro existe no catálogo, **Quando** o administrador o remove, **Então** o livro deixa de aparecer nas consultas e não permanece disponível para acesso público.

---

### Casos Limites

- Quando um usuário pesquisa um termo sem correspondência, o sistema retorna uma lista vazia com indicação clara de que nenhum livro foi encontrado.
- Quando o administrador tenta excluir uma categoria ou autor associado a livros ativos, o sistema bloqueia a exclusão e apresenta uma mensagem de impedimento.
- Quando um livro é cadastrado sem autor ou sem categoria válida, o sistema rejeita o cadastro e exige a correção dos dados obrigatórios.
- Quando há duplicidade de dados, como autores com o mesmo nome ou livros com o mesmo ISBN, o sistema impede o cadastro duplicado ou exige identificação única do registro.

## Requisitos *(obrigatório)*

### Requisitos Funcionais

- **RF-001**: O sistema DEVE permitir que usuários consultem o catálogo de livros com filtros por título, autor, categoria e termo livre.
- **RF-002**: O sistema DEVE permitir que usuários consultem os detalhes completos de um livro, incluindo autores e categorias associados.
- **RF-003**: O sistema DEVE permitir que o administrador cadastre, consulte, atualize e exclua categorias de livros.
- **RF-004**: O sistema DEVE permitir que o administrador cadastre, consulte, atualize e exclua autores.
- **RF-005**: O sistema DEVE permitir que o administrador cadastre, consulte, atualize e exclua livros, vinculando-os a autores e categorias válidos.
- **RF-006**: O sistema DEVE impedir que operações de manutenção sejam realizadas por usuários comuns e restringir essas ações apenas ao papel de administrador.
- **RF-007**: O sistema DEVE validar integridade dos dados, evitando cadastros incompletos ou inconsistentes, como livros sem título ou sem autor associado.
- **RF-008**: O sistema DEVE manter as consultas públicas consistentes com o estado atual dos dados após alterações administrativas.

### Entidades-Chave *(inclua se a funcionalidade envolver dados)*

- **Livro**: Representa uma obra do catálogo, com título, resumo, ano de publicação, ISBN, autores associados e categorias relacionadas.
- **Autor**: Representa a pessoa responsável pela criação da obra, com nome, biografia e período de atividade.
- **Categoria**: Representa uma classificação temática do catálogo, com nome e descrição.

## Critérios de Sucesso *(obrigatório)*

### Resultados Mensuráveis

- **CS-001**: Os usuários conseguem localizar livros relevantes em até 2 segundos para consultas comuns com filtros simples.
- **CS-002**: O administrador consegue concluir operações de cadastro, atualização e remoção de livros, autores e categorias com sucesso em até 5 segundos por operação em cenários normais.
- **CS-003**: Pelo menos 90% dos usuários conseguem completar uma busca principal sem assistência, identificando corretamente o livro desejado na primeira tentativa.
- **CS-004**: O catálogo mantém consistência entre consultas públicas e dados administrativos, com menos de 1% de registros inconsistentes após manutenção.

## Premissas

- Os usuários-alvo possuem acesso autenticado ou anônimo às consultas públicas, conforme a política de acesso do sistema.
- O suporte a autenticação e autorização de administradores já existe ou será fornecido por um mecanismo compartilhado do projeto.
- O catálogo inicial pode conter livros com um ou mais autores e uma ou mais categorias.
- A versão inicial não exige funcionalidades de empréstimo, estoque ou revisão editorial.
- O gerenciamento de dados é restrito ao papel de administrador e não está aberto a usuários comuns.
