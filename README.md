# ✦ Radia, Curadora Inteligente da Radia Tech

> Assistente virtual com IA generativa que ajuda mulheres em tech a navegar pelo conteúdo da Radia Tech: vagas, notícias e eventos.

Projeto desenvolvido para o desafio **"Construa Seu Assistente Virtual Com Inteligência Artificial"** da DIO.

Este repositório é a primeira versão da Radia, agente inteligente da plataforma **Radia Tech**, atualmente em construção pelo Squad Épsilon. O site e o design system completo estão sendo desenvolvidos em paralelo.

---

## O Contexto

A **Radia Tech** é uma plataforma feminista de curadoria de notícias tech, vagas e eventos, nomeada em homenagem a Radia Perlman, inventora do protocolo STP. O projeto está sendo desenvolvido pelo **Squad Épsilon**, um time acadêmico all-women.

A **Radia** é a assistente inteligente da plataforma. Ela não é um ChatGPT genérico: ela é especialista no conteúdo da Radia Tech e só responde com base no que está na plataforma.

---

## O Que a Radia Faz

| Função | Exemplo |
|---|---|
| Curadoria de notícias | "Radia, o que saiu de IA essa semana?" |
| Busca de vagas | "Radia, vagas de UX designer remoto nível pleno" |
| Guia de eventos | "Radia, tem evento de Python em Curitiba esse mês?" |
| Redirecionamento consciente | "Radia, me ensina Machine Learning" e ela indica a plataforma, não inventa um curso |

O que a Radia **não faz**:
- Não inventa vagas, links, salários ou datas
- Não dá conselhos de carreira genéricos
- Não ranqueia empregadores
- Não responde sobre temas fora da Radia Tech sem redirecionar

---

## Os 6 Passos do Desafio

| Passo | Arquivo |
|---|---|
| 1. Documentação do agente | [`docs/01-documentacao-agente.md`](docs/01-documentacao-agente.md) |
| 2. Base de conhecimento | [`docs/02-base-conhecimento.md`](docs/02-base-conhecimento.md) |
| 3. Prompts do agente | [`docs/03-prompts.md`](docs/03-prompts.md) |
| 4. Aplicação funcional | [`src/app.html`](src/app.html) |
| 5. Avaliação e métricas | [`docs/04-metricas.md`](docs/04-metricas.md) |
| 6. Pitch | [`docs/05-pitch.md`](docs/05-pitch.md) |

---

## Estrutura do Repositório

```
radia-assistente/
├── README.md
├── data/
│   ├── vagas.json         # 6 vagas mockadas
│   ├── noticias.json      # 6 notícias mockadas
│   └── eventos.json       # 6 eventos mockados
├── docs/
│   ├── 01-documentacao-agente.md
│   ├── 02-base-conhecimento.md
│   ├── 03-prompts.md
│   ├── 04-metricas.md
│   └── 05-pitch.md
└── src/
    └── app.html           # Aplicação funcional (HTML + JS Vanilla)
```

---

## Como Executar

**Via GitHub Pages (online):**
Acesse o link abaixo e cole sua API Key do Google Gemini no campo indicado dentro do chat:

👉 [Abrir a Radia](https://samaraalanna.github.io/radia-assistente/src/app.html)

A chave pode ser gerada em [aistudio.google.com](https://aistudio.google.com). Ela fica só no seu navegador e não é enviada para nenhum servidor além da OpenAI.

**Localmente:**
1. Clone o repositório
2. Abra `src/app.html` com dois cliques (abre direto no navegador, sem servidor)
3. Clique no botão ✦ no canto inferior direito
4. Cole sua API Key do Google Gemini e converse com a Radia

---

## Arquitetura (Protótipo)

```
Usuária digita pergunta
        ↓
[Painel lateral em HTML/JS Vanilla]
        ↓
[System Prompt com base de conhecimento injetada como contexto RAG simulado]
        ↓
[Google Gemini API (gemini-2.0-flash)]
        ↓
Resposta contextualizada com dados da base
```

**Nota sobre RAG:** neste protótipo, os JSONs são injetados diretamente no system prompt, simulando uma consulta RAG. Na versão de produção da Radia Tech (Next.js 14 + ASP.NET Core + PostgreSQL + Sanity CMS), a arquitetura usará embeddings com `pgvector` para busca semântica real.

---

## Stack

| Camada | Tecnologia |
|---|---|
| Interface | HTML5, CSS3 (variáveis nativas), JavaScript Vanilla ES6+ |
| IA | Google Gemini API (gemini-2.0-flash) |
| Dados | JSON mockados (vagas, notícias, eventos) |
| Dependências externas | Nenhuma |

---

## Diferenciais do Projeto

- **Interface fiel ao conceito:** painel lateral flutuante, sem sair da página
- **Zero dependências:** HTML + JS puro, sem frameworks
- **Anti-alucinação documentada:** system prompt com regras explícitas
- **Base de conhecimento realista:** JSONs com campos completos, prontos para evolução
- **Contexto de produto real:** a Radia é parte de um projeto maior (Radia Tech / Squad Épsilon)
- **Design system aplicado:** paleta, tipografia e tokens visuais da Radia Tech já refletidos na interface

---

## Sobre a Radia Tech

A Radia Tech está sendo construída pelo Squad Épsilon como projeto acadêmico:

- **Stack de produção:** Next.js 14 + ASP.NET Core + PostgreSQL + Sanity CMS
- **Missão:** curadoria de tech com perspectiva feminista
- **Nome:** homenagem a Radia Perlman, inventora do protocolo STP

---

*Desenvolvido por [Samara Alanna](https://github.com/SamaraAlanna), BORDA Design*
