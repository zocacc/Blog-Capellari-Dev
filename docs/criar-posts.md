# Como Criar Posts no Blog

Este guia explica o passo a passo para criar, revisar e publicar novos artigos em seu blog.

---

## Passo 1: Criar o Post

### Opção 1: Usando o utilitário `./blog` (Recomendado)

O script utilitário possui o comando `new` para criar posts. Na raiz do projeto, execute:

```bash
./blog new "Título do Seu Post"
```

O comando irá automaticamente:
1. Detectar o ano atual (ex: `2026`).
2. Criar a pasta e o arquivo `index.md` em `content/blog/2026/titulo-do-seu-post/index.md`.
3. Iniciar o arquivo com o template configurado em `archetypes/blog.md`.

### Opção 2: Usando o comando do Hugo

Você também pode especificar o ano e o slug manualmente:

```bash
hugo new blog/2026/titulo-do-seu-post/index.md
```

---

## Passo 2: Configurar os Metadados (Frontmatter)

Abra o arquivo gerado e configure os campos no cabeçalho (delimitados por `---`):

```yaml
---
title: 'Título do Seu Post'               # Título principal do post
date: 2026-07-08T12:00:00Z                # Data de publicação (UTC)
lastmod: 2026-07-08T12:00:00Z             # Data de última modificação
slug: 'titulo-do-seu-post'                # Parte final da URL do post
draft: false                              # Mude para false para o post ficar visível
description: "Breve resumo do artigo."    # Descrição para SEO e exibição nos cards
image: "/images/capivara-eng.png"         # Imagem de capa (salvar em static/images/)
categories:                               # Categoria principal
  - Carreira e Aprendizado
tags:                                     # Assuntos/Tags secundárias
  - hugo
  - redes
authors:                                  # Autor do post
  - name: Enzo Capellari
toc: true                                 # Exibir sumário/tabela de conteúdos
---
```

> [!IMPORTANT]
> **Imagens de capa**: Salve as imagens na pasta `static/images/` e no frontmatter refira-se a elas iniciando com a barra raiz, por exemplo `/images/sua-imagem.png`.

---

## Passo 3: Escrever o Conteúdo

Escreva abaixo do segundo `---` utilizando formatação Markdown convencional. Você pode usar:
- Títulos: `## Subtítulo`, `### Sub-subtítulo`.
- Citações: `> "Não terceirize suas decisões."`.
- Blocos de código com sintaxe colorida:
  \`\`\`python
  def ola_mundo():
      print("Olá!")
  \`\`\`

---

## Passo 4: Pré-visualizar Localmente

Para rodar o servidor de desenvolvimento e testar como o post ficou em tempo real:

```bash
./blog dev
```

Abra o navegador no endereço exibido (geralmente [http://localhost:1313](http://localhost:1313)). Quaisquer edições feitas nos arquivos markdown recarregam a página automaticamente.

---

## Passo 5: Publicar

Quando o post estiver pronto para ir ao ar, certifique-se de definir `draft: false` nos metadados e execute o comando de publicação:

```bash
./blog publish
```

Esse comando irá gerar o build minificado de produção e sincronizar os arquivos para o servidor web configurado.
