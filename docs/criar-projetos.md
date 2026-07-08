# Como Criar Projetos no Portfolio

Este guia explica como adicionar novos projetos ao portfólio de forma rápida e padronizada.

---

## Opção 1: Usando o utilitário `./blog` (Recomendado)

O script utilitário possui o comando `project` que automatiza a criação do arquivo e das URLs com base no seu usuário do GitHub (`zocacc`).

1. Na raiz do projeto, execute no terminal:
   ```bash
   ./blog project "Nome do Seu Projeto"
   ```
2. O script irá criar o arquivo `index.md` dentro de uma nova pasta sob `content/projetos/`.
   - Exemplo de caminho: `content/projetos/nome-do-seu-projeto/index.md`
3. O terminal exibirá o caminho do arquivo gerado.

---

## Opção 2: Usando o comando do Hugo

Você também pode criar a estrutura diretamente pelo CLI do Hugo:

```bash
hugo new projetos/nome-do-seu-projeto/index.md
```

Como existe um modelo configurado em `archetypes/projetos.md`, as propriedades iniciais serão preenchidas automaticamente.

---

## Estrutura de Metadados (Frontmatter)

Após criar o projeto, abra o arquivo `index.md` correspondente e preencha/ajuste os campos no topo do arquivo (delimitados por `---`):

```yaml
---
title: 'Nome Do Seu Projeto'                    # Título de exibição amigável
date: 2026-07-08T15:24:20Z                      # Data de criação
lastmod: 2026-07-08T15:24:20Z                   # Data da última modificação
type: projects                                  # Define o layout correto do portfólio
description: "Breve resumo do seu projeto."      # Texto exibido nos cards da listagem
status: Público                                 # Status atual (ex: Rascunho, Em Desenvolvimento, Público, Concluído)
featured: false                                 # Defina como 'true' para destacar na página inicial
weight: 10                                      # Define a ordem na lista (números menores aparecem primeiro)
repo: zocacc/nome-do-seu-projeto                # Repositório no formato usuario/projeto
github: https://github.com/zocacc/nome-do-seu-projeto # Link direto para o repositório
technologies:                                   # Linguagens e ferramentas utilizadas
  - Go
  - Docker
lessons:                                        # Principais aprendizados práticos obtidos
  - Aprendizado número 1 sobre o projeto.
  - Aprendizado número 2 sobre o projeto.
---
```

## Conteúdo Detalhado

Abaixo do segundo `---` no arquivo `index.md`, escreva em Markdown todo o detalhamento técnico do projeto, arquitetura adotada, desafios enfrentados e imagens, se houver. Esse conteúdo será exibido na página dedicada do projeto.
