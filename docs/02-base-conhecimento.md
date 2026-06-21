# 02 — Base de Conhecimento

## Estrutura dos Dados

A base de conhecimento da Radia é composta por três arquivos JSON mockados que simulam o conteúdo real da Radia Tech:

| Arquivo | Registros | Descrição |
|---|---|---|
| `data/vagas.json` | 6 vagas | Oportunidades com empresa, nível, localização, stack e salário |
| `data/noticias.json` | 6 notícias | Artigos categorizados por área tech com tags |
| `data/eventos.json` | 6 eventos | Conferências, meetups e workshops com data e cidade |

---

## Estratégia de Injeção (RAG Simulado)

Neste protótipo, os três arquivos são serializados para JSON e injetados diretamente no **system prompt** antes de cada conversa. Isso simula o comportamento de um sistema RAG real, onde o agente consultaria um banco vetorial ou SQL antes de responder.

**Formato de injeção no system prompt:**
```
VAGAS DISPONÍVEIS NA PLATAFORMA:
[conteúdo de vagas.json serializado]

NOTÍCIAS RECENTES:
[conteúdo de noticias.json serializado]

EVENTOS PRÓXIMOS:
[conteúdo de eventos.json serializado]
```

---

## Campos Relevantes por Tipo

### Vagas
- `titulo`, `empresa`, `local`, `nivel`, `area`, `stack`, `salario`, `link`, `publicada_em`
- Filtros principais: área, nível, localização (remoto vs. presencial)

### Notícias
- `titulo`, `categoria`, `resumo`, `fonte`, `link`, `publicada_em`, `tags`
- Filtros principais: categoria, tags, data de publicação

### Eventos
- `nome`, `tipo`, `area`, `cidade`, `estado`, `formato`, `data_inicio`, `gratuito`, `preco`, `link`
- Filtros principais: cidade/estado, área, formato (online/presencial), gratuidade

---

## Extensão para Produção

Na versão real da Radia Tech (Next.js 14 + ASP.NET Core + PostgreSQL + Sanity CMS):

- Vagas e eventos seriam consultados via query PostgreSQL com filtros dinâmicos
- Notícias viriam do Sanity CMS via GROQ query
- O RAG real usaria embeddings (ex: `text-embedding-3-small`) indexados no `pgvector`
- A Radia receberia apenas os top-K resultados relevantes, não a base inteira
