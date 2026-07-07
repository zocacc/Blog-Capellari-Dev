# Capellari Dev

Blog em Hugo + Hextra com dois alvos operacionais:

- preview local no devcontainer em `http://localhost:1313`
- publicacao estatica em `/opt/capellari-dev/public`, servida por Caddy com HTTPS automático no domínio `enzocapellari.is-a.dev` (e fallback HTTP na porta `80` para acesso via IP)

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
- campos de `description`, `image`, `categories`, `tags`, `authors` e `toc`

### `./blog dev`

Sobe o preview local pelo devcontainer em `http://localhost:1313`.

Use esse comando enquanto escreve ou revisa um post.

### `./blog build`

Gera a build de producao em `public/` dentro do fluxo padronizado do container.

### `./blog publish`

Executa o build e sincroniza o conteudo de `public/` para `/opt/capellari-dev/public/`.

No final, garante que o Caddy de producao continue ativo e recarrega as novas diretivas de domínio e TLS.

## Estrutura de conteudo e Layouts

### Customizações Recentes
- **Página Inicial:** A seção de artigos recentes foi movida para o topo para dar destaque total ao blog. O post mais recente é exibido em destaque em um card maior (`.featured-article-card`) com efeito de gradiente.
- **Post Individual:** Cabeçalho otimizado contendo metadados (data de publicação, tempo de leitura) e, ao final de cada artigo, é exibido um cartão de biografia do autor (Sobre o Autor) integrado com o avatar do GitHub.

### Imagens nos Artigos
É possível definir imagens de destaque para cada artigo. O arquétipo base já inclui o parâmetro `image`.
1. Coloque a imagem dentro de `static/images/` (ex: `static/images/meu-post-banner.jpg`).
2. Adicione o parâmetro no front matter do arquivo Markdown do post:
```yaml
image: "/images/meu-post-banner.jpg"
```
- No card de destaque da Home, a imagem será renderizada na seção visual direita.
- Nos cards de listagem comuns, a imagem será exibida como um pequeno banner superior.
- No post individual, ela será exibida como cabeçalho de destaque logo abaixo do título.

### Estrutura de Pastas
Posts do blog devem ficar neste formato:

```text
content/blog/2026/meu-post/index.md
```

A URL final segue o `slug` definido no front matter:

```text
/blog/2026/meu-post/
```

## HTTPS e Domínio (`enzocapellari.is-a.dev`)

O Caddy gerencia automaticamente o HTTPS utilizando certificados SSL gratuitos do Let's Encrypt / ZeroSSL.

Para que funcione:
1. Garanta o apontamento DNS tipo `A` de `enzocapellari.is-a.dev` para o IP do servidor `168.75.66.170`.
2. Habilite a porta `443/TCP` (HTTPS) nas regras de entrada (**Ingress Rules**) da Security List na Oracle Cloud.
3. Caddyfile de produção está configurado em `/opt/capellari-dev/Caddyfile` mapeando o domínio e mantendo a porta `:80` ativa para fallbacks.

## Ambiente

O fluxo oficial de `new`, `dev`, `build` e `publish` roda sempre via devcontainer para evitar divergencia de versao do Hugo entre host e container.

O workflow de GitHub Pages em [`.github/workflows/pages.yaml`](./.github/workflows/pages.yaml) permanece isolado desse fluxo local/servidor.
