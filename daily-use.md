# Uso Diario do Blog

Este guia resume o fluxo diario para criar, revisar e publicar posts no blog sem precisar lembrar comandos do Hugo, Docker ou Caddy.

## 1. Preparar o ambiente

Rode uma vez no inicio ou sempre que ajustar permissao, container ou producao:

```bash
./blog bootstrap
```

Esse comando:

- sobe o devcontainer
- corrige permissao de `public/`
- corrige permissao de `/opt/capellari-dev/public`
- valida e sobe o Caddy de producao

## 2. Criar um novo post

Crie o post informando apenas o titulo:

```bash
./blog new "Meu novo post"
```

O script cria um arquivo neste formato:

```text
content/blog/ANO/slug-do-post/index.md
```

Exemplo:

```text
content/blog/2026/meu-novo-post/index.md
```

O arquivo ja nasce com:

- `title`
- `date`
- `lastmod`
- `slug`
- `draft: true`
- `description`
- `categories`
- `tags`
- `authors`
- `toc`

## 3. Editar o conteudo

Abra o arquivo criado e preencha o post.

Fluxo recomendado:

1. Escreva o conteudo principal.
2. Preencha `description`.
3. Ajuste `tags` e `categories`.
4. Quando quiser que o post apareca normalmente no site, troque:

```yaml
draft: true
```

por:

```yaml
draft: false
```

## 4. Testar localmente

Suba o preview local:

```bash
./blog dev
```

Depois abra:

```text
http://localhost:1313
```

Use esse modo para revisar:

- texto
- estrutura do artigo
- links
- headings
- listagem do blog
- URL final do post

Para parar o preview, use `Ctrl+C`.

## 5. Gerar a build local

Se quiser apenas verificar a geracao de producao sem publicar:

```bash
./blog build
```

Esse comando gera a pasta:

```text
public/
```

## 6. Publicar em producao

Quando estiver satisfeito com o post:

```bash
./blog publish
```

Esse comando:

1. roda o build de producao
2. sincroniza `public/` para `/opt/capellari-dev/public/`
3. garante que o Caddy continue em execucao

Depois disso, o site servido na porta 80 ja deve refletir a nova versao.

## 7. Fluxo mais comum no dia a dia

Para um post novo, o fluxo normal fica assim:

```bash
./blog new "Titulo do post"
./blog dev
# editar o arquivo do post
./blog build
./blog publish
```

## 8. Quando usar cada comando

- `./blog bootstrap`: quando preparar o ambiente ou corrigir permissoes.
- `./blog new "Titulo"`: quando iniciar um post novo.
- `./blog dev`: quando quiser revisar o site em `localhost:1313`.
- `./blog build`: quando quiser validar a build sem publicar.
- `./blog publish`: quando quiser enviar a versao atual para producao.

## 9. Erros comuns

### O post nao aparece no blog

Verifique se o arquivo tem:

```yaml
draft: false
```

### O slug ficou diferente do que voce esperava

O slug vem do titulo informado no `./blog new`. Se precisar mudar a URL, ajuste manualmente o campo:

```yaml
slug: "meu-slug"
```

### O build falhou por permissao

Rode novamente:

```bash
./blog bootstrap
```

### O preview nao abriu na 1313

Confirme se o container subiu e se a porta nao esta ocupada. Em seguida rode de novo:

```bash
./blog dev
```

## 10. Regra pratica

Se a meta for simples, pense assim:

- escrever e revisar: `./blog dev`
- gerar saida local: `./blog build`
- colocar no ar: `./blog publish`
