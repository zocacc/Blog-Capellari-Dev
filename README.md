# Capellari Dev

Blog em Hugo + Hextra com dois alvos operacionais:

- preview local no devcontainer em `http://localhost:1313`
- publicacao estatica em `/opt/capellari-dev/public`, servida por Caddy na porta `80`

## Fluxo diario

Todos os comandos do projeto ficam centralizados no script `./blog`.

```bash
./blog bootstrap
./blog new "Meu novo post"
./blog dev
./blog build
./blog publish
```

## Comandos

### `./blog bootstrap`

Uso inicial para preparar o ambiente:

- sobe o devcontainer do projeto
- corrige permissao de `public/`
- corrige permissao de `/opt/capellari-dev/public`
- valida e sobe o Caddy de producao

Execute uma vez antes do primeiro preview ou publish.

### `./blog new "Titulo do post"`

Cria um post em `content/blog/<ano>/<slug>/index.md` usando `archetypes/blog.md`.

O arquivo nasce com:

- `draft: true`
- `slug` consistente com a URL
- campos de `description`, `categories`, `tags`, `authors` e `toc`

### `./blog dev`

Sobe o preview local pelo devcontainer em `http://localhost:1313`.

Use esse comando enquanto escreve ou revisa um post.

### `./blog build`

Gera a build de producao em `public/` dentro do fluxo padronizado do container.

### `./blog publish`

Executa o build e sincroniza o conteudo de `public/` para `/opt/capellari-dev/public/`.

No final, garante que o Caddy de producao continue ativo.

## Estrutura de conteudo

Posts do blog devem ficar neste formato:

```text
content/blog/2026/meu-post/index.md
```

A URL final segue o `slug` definido no front matter:

```text
/blog/2026/meu-post/
```

## Ambiente

O fluxo oficial de `new`, `dev`, `build` e `publish` roda sempre via devcontainer para evitar divergencia de versao do Hugo entre host e container.

O workflow de GitHub Pages em [`.github/workflows/pages.yaml`](./.github/workflows/pages.yaml) permanece isolado desse fluxo local/servidor.
