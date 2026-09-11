# 🚀 Desafio Git & GitHub — Desenvolvimento Colaborativo

Este desafio tem como objetivo simular um fluxo de desenvolvimento próximo ao utilizado por equipes de software.

Aqui, **não será avaliado apenas se o sistema funciona**.

Também queremos entender **como o sistema foi construído**.

O GitHub será o diário de desenvolvimento da equipe.

---

## 🎯 Objetivo

Cada equipe deverá organizar seu projeto utilizando:

- Backlog
- Issues
- Branches
- Commits
- Pull Requests
- Code Review
- Merge
- Kanban / GitHub Projects
- README

O fluxo esperado durante o desenvolvimento será:

```text
Issue
  ↓
Branch
  ↓
Código
  ↓
Commit
  ↓
Pull Request
  ↓
Code Review
  ↓
Merge
```

> 💡 Não queremos apenas ver o resultado final.
> Queremos conseguir acompanhar a história do desenvolvimento pelo GitHub.

---

# 👥 Equipes

Cada equipe deverá possuir entre **3 e 5 integrantes**.

Todos os integrantes precisam participar do desenvolvimento e aparecer no histórico do repositório.

A participação poderá ser demonstrada através de:

- Issues
- Commits
- Branches
- Pull Requests
- Code Reviews
- Discussões técnicas
- Organização do projeto

Colocar apenas o nome no README **não comprova participação**.

---

# 🟢 Situação A — Minha equipe ainda não começou

Sem problemas.

Vocês receberão um problema e deverão construir o projeto seguindo todo o fluxo proposto neste desafio.

### Exemplo de problema

> 🍔 Um restaurante precisa de um site para apresentar seu cardápio aos clientes.

O sistema deverá permitir visualizar, no mínimo:

- Nome do restaurante
- Cardápio
- Produtos
- Descrição dos produtos
- Valores
- Endereço/localização
- Informações de contato

A equipe deverá primeiro discutir o problema e transformar os requisitos em tarefas.

Não comecem programando.

Comecem planejando.

```text
Problema
    ↓
Backlog
    ↓
Issues
    ↓
Desenvolvimento
```

---

# 🔵 Situação B — Minha equipe já começou o projeto

Ótimo.

Vocês **não precisam recomeçar o projeto**.

A missão será organizar o desenvolvimento existente utilizando o fluxo apresentado neste desafio.

A equipe deverá analisar:

- O que já foi desenvolvido?
- O que ainda precisa ser desenvolvido?
- Quais funcionalidades podem virar Issues?
- Quais funcionalidades precisam de branches?
- Os commits estão claros?
- Existe uma estratégia de branches?
- Existem Pull Requests?
- Existe Code Review?
- A `main` está estável?

A partir deste momento, as próximas funcionalidades deverão seguir o fluxo:

```text
Issue → Branch → Código → Commit → Pull Request → Review → Merge
```

---

# 🌳 Estratégia de Branches

Para este desafio utilizaremos uma estratégia simplificada:

```text
main
 │
 └── dev
      │
      ├── feature/cardapio
      ├── feature/localizacao
      ├── feature/contato
      └── fix/corrige-preco
```

### `main`

Representa a versão **estável** do projeto.

Evitem desenvolver diretamente nela.

### `dev`

Representa a versão de **desenvolvimento e integração**.

As funcionalidades desenvolvidas pela equipe serão integradas primeiro aqui.

### `feature/*`

Utilizada para desenvolver funcionalidades.

Exemplos:

```text
feature/cardapio
feature/cadastro-produto
feature/localizacao
feature/pagina-contato
```

### `fix/*`

Utilizada para correções.

```text
fix/validacao-formulario
fix/preco-produto
fix/menu-mobile
```

---

# 👨‍💻 Organização da equipe

A equipe deverá discutir e definir responsabilidades.

Uma sugestão para a dinâmica é:

### Responsável pela `main`

Cuida da estabilidade da versão principal.

A integração normalmente seguirá:

```text
dev → Pull Request → main
```

Esse integrante não precisa ser o único que trabalha com a `main`, mas pode atuar como responsável por garantir que apenas código revisado seja integrado.

### Responsável pela integração em `dev`

Ajuda a organizar os Pull Requests:

```text
feature/* → Pull Request → dev
```

Também verifica:

- conflitos;
- qualidade do PR;
- descrição;
- vínculo com Issue;
- aprovação do Code Review.

### Desenvolvedores

Trabalham nas Issues através de branches específicas.

Exemplo:

```text
Issue #12
   ↓
feature/cardapio
   ↓
Commits
   ↓
Pull Request
   ↓
dev
```

> ⚠️ Responsabilidade não significa exclusividade.
> Todos devem compreender o fluxo Git utilizado pela equipe.

---

# 🎫 Padrão de Issues

Cada tarefa relevante deverá possuir uma Issue.

Utilizem o seguinte modelo:

```markdown
## 📌 Descrição

Descreva de forma objetiva o que precisa ser desenvolvido.

## 🎯 Objetivo

Explique por que essa tarefa é necessária para o projeto.

## ✅ Critérios de Aceitação

- [ ] Critério 1
- [ ] Critério 2
- [ ] Critério 3

## 🛠️ Tarefas Técnicas

- [ ] Criar estrutura necessária
- [ ] Implementar funcionalidade
- [ ] Validar funcionamento
- [ ] Testar alterações

## 🔗 Informações adicionais

Adicione referências, imagens, protótipos ou outras informações relevantes.
```

### Exemplo

```markdown
# Criar seção de cardápio

## 📌 Descrição

Criar uma seção responsável por apresentar os produtos disponíveis no restaurante.

## 🎯 Objetivo

Permitir que o cliente consulte o cardápio antes de visitar o estabelecimento.

## ✅ Critérios de Aceitação

- [ ] Exibir nome do produto
- [ ] Exibir descrição
- [ ] Exibir preço
- [ ] Layout funcionar em dispositivos móveis

## 🛠️ Tarefas Técnicas

- [ ] Criar estrutura HTML
- [ ] Criar estilização
- [ ] Cadastrar produtos
- [ ] Validar responsividade
```

---

# 🌿 Criando uma Branch a partir da Issue

Suponha que exista:

```text
Issue #12 — Criar seção de cardápio
```

Uma possível branch seria:

```bash
git switch dev
git pull

git switch -c feature/12-cardapio
```

Assim conseguimos relacionar facilmente:

```text
Issue #12
     ↓
feature/12-cardapio
```

---

# 💬 Conventional Commits

Os commits deverão explicar claramente o que aconteceu no projeto.

Formato:

```text
<tipo>: <descrição>
```

Exemplos:

```bash
git commit -m "feat: adiciona seção de cardápio"

git commit -m "fix: corrige preço dos produtos"

git commit -m "docs: atualiza instruções do projeto"

git commit -m "refactor: reorganiza componente de produtos"

git commit -m "style: ajusta layout do cardápio"

git commit -m "test: adiciona testes do formulário"

git commit -m "chore: atualiza dependências"
```

Evitem:

```text
alteração

teste

final

final2

agora vai

corrigido

commit
```

> Um bom histórico deve permitir entender a evolução do projeto sem precisar abrir todos os arquivos.

---

# 🔀 Padrão de Pull Request

Todo Pull Request deverá explicar claramente **o que está sendo integrado e por quê**.

Utilizem:

```markdown
## 📌 O que foi desenvolvido?

Descreva resumidamente as alterações realizadas.

## 🎯 Issue relacionada

Closes #NUMERO_DA_ISSUE

## 🛠️ O que foi alterado?

- Alteração 1
- Alteração 2
- Alteração 3

## 🧪 Como testar?

1. Execute o projeto
2. Acesse...
3. Realize...
4. Verifique se...

## 📸 Evidências

Adicione prints, vídeos ou GIFs quando fizer sentido.

## ✅ Checklist

- [ ] O código executa corretamente
- [ ] Testei minhas alterações
- [ ] Não deixei código comentado/desnecessário
- [ ] Meu PR possui uma descrição clara
- [ ] Minha branch está atualizada
- [ ] Minha Issue foi vinculada
- [ ] Solicitei Code Review
```

---

# 🔍 Code Review

Abrir o Pull Request **não significa que ele deve ser imediatamente aceito**.

Outro integrante deverá revisar.

O reviewer deve observar:

- O código funciona?
- Resolve a Issue?
- Os critérios de aceitação foram atendidos?
- Existe código desnecessário?
- Os nomes estão claros?
- Existe alguma regressão?
- O código pode ser entendido por outra pessoa?

Comentários como:

```text
"LGTM"
```

são válidos quando realmente houve revisão, mas incentivamos feedbacks mais úteis quando necessário:

```text
Sugestão: podemos extrair essa validação para uma função
para evitar repetir essa lógica.
```

ou:

```text
O critério de responsividade da Issue ainda não parece
funcionar em telas menores. Poderia verificar?
```

---

# 🔄 Fluxo esperado

Para cada funcionalidade:

```text
┌───────────────┐
│     ISSUE     │
└───────┬───────┘
        ↓
┌───────────────┐
│    BRANCH     │
└───────┬───────┘
        ↓
┌───────────────┐
│    CÓDIGO     │
└───────┬───────┘
        ↓
┌───────────────┐
│    COMMITS    │
└───────┬───────┘
        ↓
┌───────────────┐
│ PULL REQUEST  │
└───────┬───────┘
        ↓
┌───────────────┐
│  CODE REVIEW  │
└───────┬───────┘
        ↓
┌───────────────┐
│     MERGE     │
└───────────────┘
```

Para integração:

```text
feature/* ──PR──► dev ──PR──► main
```

---

# 📋 Backlog e Kanban

As Issues deverão estar organizadas no quadro da equipe.

Sugestão:

```text
📋 BACKLOG
     ↓
📝 A FAZER
     ↓
🚧 EM DESENVOLVIMENTO
     ↓
👀 EM REVISÃO
     ↓
✅ CONCLUÍDO
```

Uma Issue deve acompanhar o desenvolvimento.

Por exemplo:

```text
Issue criada
     ↓
A FAZER

Branch criada
     ↓
EM DESENVOLVIMENTO

Pull Request aberto
     ↓
EM REVISÃO

Merge realizado
     ↓
CONCLUÍDO
```

---

# 🏁 Critérios de Avaliação

Não será avaliado somente o resultado final.

Será avaliado **todo o roadmap do repositório**.

### 1. 💻 Produto funcionando

O projeto executa e atende ao problema proposto?

### 2. 📋 Backlog e Kanban

A equipe planejou e acompanhou suas tarefas?

### 3. 💬 Commits claros

Os commits contam uma história compreensível?

### 4. 🌿 Branches e Pull Requests

As funcionalidades foram desenvolvidas de forma organizada?

### 5. 👀 Code Review

A equipe realmente revisou o código antes dos merges?

### 6. 👤 Participação individual

É possível identificar a contribuição de cada integrante através do histórico?

---

# 🔎 O GitHub contará a história

No final da atividade, devemos conseguir navegar pelo repositório e encontrar:

```text
Backlog
   ↓
Issues
   ↓
Branches
   ↓
Commits
   ↓
Pull Requests
   ↓
Code Reviews
   ↓
Merges
   ↓
Produto final
```

Se conseguirmos entender **como o projeto foi construído apenas analisando o repositório**, a equipe criou um bom processo de desenvolvimento.

---

# Assinado e Criado por:

```text
Paulo André Santos Queiroz
```
