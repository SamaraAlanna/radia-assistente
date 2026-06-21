# 05 — Pitch: Radia, a Curadora Inteligente da Radia Tech

## O Problema

Mulheres em tech passam horas por semana garimpando informação dispersa: vagas no LinkedIn, notícias no Twitter, eventos no Sympla, tudo ao mesmo tempo, em plataformas que não foram pensadas para elas.

A Radia Tech existe para mudar isso — uma plataforma feminista de curadoria de tech, nomeada em homenagem a Radia Perlman, inventora do protocolo STP.

## A Solução

A **Radia** é a assistente inteligente da Radia Tech. Ela não é um ChatGPT genérico — ela é uma especialista no conteúdo da plataforma.

Em vez de você filtrar, a Radia filtra por você:
- "Radia, vagas de UX remoto pleno" → lista na hora, com salário e link
- "Radia, notícias de IA essa semana" → curadoria em segundos
- "Radia, evento de Python em Curitiba" → data, local e se é gratuito

## O Diferencial

A Radia opera com **RAG** — antes de responder, ela consulta o banco real da plataforma. Ela nunca inventa uma vaga, uma data ou um link. Se não tem, ela diz que não tem.

Isso é o que separa a Radia de um chatbot genérico: ela é especialista, não generalista.

## A Tecnologia

| Camada | Tecnologia |
|---|---|
| Interface | HTML/CSS/JS Vanilla — painel lateral flutuante |
| IA | Anthropic Claude (API) |
| Dados | JSONs mockados simulando RAG |
| Produção (futura) | Next.js 14 + PostgreSQL + pgvector + Sanity CMS |

## O Contexto

A Radia foi desenvolvida como parte do projeto **Squad Épsilon** — um time acadêmico all-women construindo a Radia Tech como projeto de conclusão de curso, com stack: Next.js 14, ASP.NET Core, PostgreSQL e Sanity CMS.

## Resultado

Um assistente que economiza tempo, reduz ruído de informação e coloca conteúdo relevante na mão de quem mais precisa — na plataforma que foi feita para ela.

> "A Radia não responde tudo. Ela responde o que importa pra você."
