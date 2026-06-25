---
title: Criando meu blog com Hugo, Hextra e GitHub
date: 2026-06-25
lastmod: 2026-06-25
draft: true
description: Primeira versão do texto que explica por que este blog existe e por que a base técnica foi construída com Hugo, Hextra, Markdown e GitHub.
categories:
  - Projetos
  - Carreira e Aprendizado
tags:
  - hugo
  - hextra
  - github
  - markdown
  - documentação
authors:
  - name: Enzo Capellari
toc: true
---

Criar um blog técnico em 2026 pode parecer uma escolha estranha quando quase toda publicação já cabe em uma rede social, em uma thread ou em um post curto com algum tom de anúncio. Ainda assim, a principal razão para abrir este espaço é simples: eu quero um lugar em que o raciocínio técnico caiba inteiro.

Grande parte do que eu estudo e desenvolvo não aparece de forma honesta em formatos rápidos. Quando estou tentando entender um problema de rede, automatizar uma tarefa repetitiva, revisar um log, montar um ambiente local, testar uma API ou depurar um circuito, o resultado final costuma ser só uma parte pequena do trabalho. O que realmente gera aprendizado é o caminho entre a dúvida inicial e a solução viável. Esse caminho inclui contexto, hipóteses erradas, decisões provisórias, testes descartados e ajustes de direção. Em geral, é justamente essa parte que some quando tudo vira só um post curto dizendo que "deu certo".

Este blog nasce para registrar esse processo de forma mais completa. A ideia é documentar projetos, estudos, experimentos, erros, decisões técnicas e evolução profissional sem precisar fingir um nível de domínio que eu ainda estou construindo. Quero usar este espaço para deixar claro o que eu sei, o que ainda estou aprendendo e o que precisei investigar para chegar a determinado resultado. Isso me parece mais útil do que tentar manter uma vitrine em que tudo já aparece pronto.

Também existe uma razão prática para preferir um espaço próprio. Plataformas terceiras mudam regras, interface, alcance e formato o tempo todo. Um site estático em um repositório controlado por mim me dá autonomia sobre estrutura, histórico e publicação. Se eu quiser reorganizar categorias, revisar um texto antigo, corrigir uma decisão ruim de arquitetura ou até migrar o visual inteiro do site, eu faço isso trabalhando em arquivos versionados, sem depender de uma plataforma centralizada ou de um editor visual limitado.

Escolher **Markdown** como formato principal veio exatamente dessa busca por simplicidade e longevidade. Markdown reduz atrito. Eu consigo escrever rápido, revisar em qualquer editor, versionar mudanças com clareza e manter o foco no conteúdo. Para um blog que pretende registrar aprendizado real, isso importa bastante. Quanto menor o esforço para publicar, maior a chance de eu documentar o que está acontecendo enquanto ainda estou no meio de um problema, e não só semanas depois, quando a memória já filtrou os detalhes desconfortáveis.

Outra vantagem do Markdown é que ele se encaixa bem em conteúdo técnico. Blocos de código, listas, tabelas simples, trechos de configuração e pequenas notas de troubleshooting funcionam sem exagero de formatação. Se eu estiver escrevendo sobre Python, GitHub Actions, Linux, GPON, APIs, PostgreSQL, microcontroladores ou qualquer outro tema que dependa de exemplos concretos, eu consigo estruturar o texto de maneira objetiva e legível. O conteúdo continua portátil, fácil de revisar e simples de manter.

Para transformar esses arquivos em site, escolhi o **Hugo**. O motivo principal é pragmático: ele resolve muito bem o que eu preciso agora sem empurrar uma stack maior do que o necessário. Quero um blog estático, rápido, previsível e fácil de versionar. Hugo entrega isso com uma estrutura simples, build rápido e dependência operacional baixa. Não há necessidade de backend, banco de dados, pipeline complexo de frontend ou um conjunto grande de ferramentas para algo cujo centro deveria ser o texto e a documentação.

O tema **Hextra** entrou na escolha pelo mesmo motivo. Ele já fornece uma base limpa, boa legibilidade, busca nativa, modo claro e escuro, navegação organizada e destaque de código sem exigir que eu construa tudo do zero. Em vez de gastar energia criando uma interface inteira antes mesmo de publicar o primeiro artigo, eu consigo partir de uma base sólida e ajustar identidade, conteúdo e estrutura com calma. Para este momento, isso é mais valioso do que buscar uma personalização total desde o primeiro dia.

Também gostei do fato de o Hextra não empurrar o site para uma estética excessivamente promocional. Eu não quero transformar este blog em uma landing page corporativa. O objetivo é parecer um espaço técnico pessoal: simples, legível, profissional e honesto. Se no futuro fizer sentido adicionar mais seções, destacar projetos específicos ou organizar séries de artigos, a base já permite essa evolução sem que eu precise recomeçar a arquitetura do site.

Versionar tudo no **GitHub** fecha essa decisão de forma natural. O repositório funciona como fonte de verdade do blog. Nele ficam configuração, conteúdo, histórico de mudanças e estrutura dos projetos. Isso facilita revisão, rastreabilidade e manutenção. Se eu alterar um texto antigo, consigo ver exatamente o que mudou. Se eu testar uma nova organização para a homepage, consigo revisar o diff. Se eu quiser automatizar verificações de build, revisar links internos ou preparar deploy, o GitHub conversa bem com esse fluxo desde o início.

Mais importante do que isso, manter o blog como código reforça o próprio posicionamento do site. Não é apenas um lugar para publicar texto sobre tecnologia. É também um projeto técnico em si. A estrutura do blog, a organização dos conteúdos, as decisões de layout, os ajustes de SEO, a forma de escrever em bundles por página e a manutenção do tema fazem parte do aprendizado que eu quero registrar. O site não é só vitrine; ele também é laboratório.

Quanto à evolução daqui para frente, eu espero que este espaço cresça em algumas direções diferentes. A primeira é o registro de projetos reais, com contexto suficiente para que um texto seja útil mesmo quando o resultado ainda está incompleto. A segunda é a documentação de estudos e experimentos, especialmente quando eu precisar entender melhor uma ferramenta, protocolo, linguagem ou componente eletrônico. A terceira é construir uma referência pública do meu percurso técnico, algo que faça mais sentido do que apenas listar tópicos soltos em um perfil.

Isso significa que nem todo artigo daqui será um tutorial fechado. Alguns textos vão ser relatos de investigação. Outros vão ser notas de implementação. Alguns talvez mostrem uma solução razoável para um problema pequeno. Outros podem registrar erros, limitações ou uma abordagem que eu abandonei depois. Esse formato me interessa porque representa melhor a prática real de engenharia: trabalho iterativo, decisões sob restrição, revisão constante e aprendizado acumulado em camadas.

Se este blog cumprir bem seu papel, ele vai se tornar um arquivo público da minha evolução técnica. Não um arquivo perfeito, nem uma linha do tempo cuidadosamente editada para parecer sempre ascendente, mas um registro útil de como eu penso, testo, documento e aprendo. Para mim, isso já é uma justificativa suficiente para manter um espaço próprio.

O primeiro passo, então, não é publicar uma coleção de resultados prontos. É construir uma base simples, estável e fácil de manter, e começar a registrar o que realmente está acontecendo durante os projetos. Esse texto existe para marcar esse ponto de partida.
