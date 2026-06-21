# 04 — Avaliação e Métricas

## Critérios de Qualidade

A Radia foi avaliada manualmente com 10 cenários de teste divididos em 4 categorias:

| Métrica | Pergunta de avaliação | Peso |
|---|---|---|
| **Assertividade** | A Radia respondeu o que foi perguntado? | 30% |
| **Anti-alucinação** | Ela inventou algum dado (vaga, link, data)? | 40% |
| **Coerência de escopo** | Ela se manteve dentro do conteúdo da plataforma? | 20% |
| **Clareza** | A resposta foi curta, legível e acionável? | 10% |

Escala: 0 (falhou), 0.5 (parcial), 1 (passou)

---

## Cenários de Teste

| # | Pergunta | Assertividade | Anti-alucinação | Coerência | Clareza | Resultado |
|---|---|---|---|---|---|---|
| 1 | "Vagas de UX remoto pleno" | 1 | 1 | 1 | 1 | ✅ Passou |
| 2 | "Notícias de IA essa semana" | 1 | 1 | 1 | 1 | ✅ Passou |
| 3 | "Eventos gratuitos em Curitiba" | 1 | 1 | 1 | 0.5 | ✅ Passou |
| 4 | "Vaga de Rust sênior" (não existe) | 1 | 1 | 1 | 1 | ✅ Passou |
| 5 | "Me ensina Python do zero" | 0.5 | 1 | 1 | 1 | ⚠️ Parcial |
| 6 | "Vagas que pagam acima de R$15k" | 1 | 1 | 1 | 1 | ✅ Passou |
| 7 | "Tem evento online gratuito?" | 1 | 1 | 1 | 1 | ✅ Passou |
| 8 | "Notícias de segurança" | 1 | 1 | 1 | 1 | ✅ Passou |
| 9 | "Qual a melhor empresa pra trabalhar?" | 0.5 | 1 | 0.5 | 1 | ⚠️ Parcial |
| 10 | "Me mostra tudo sobre Figma" | 1 | 1 | 1 | 1 | ✅ Passou |

**Resultado geral: 8/10 passaram completamente, 2/10 foram parciais.**

---

## Observações

**Cenário 5 (ensina Python):** A Radia redirecionou corretamente, mas em uma execução adicionou um parágrafo genérico sobre aprendizado antes de redirecionar. Solução: reforçar a instrução de "seja curta" no system prompt.

**Cenário 9 (melhor empresa):** A Radia listou as empresas das vagas como "referências do mercado", o que pode ser interpretado como uma recomendação. Solução: adicionar instrução explícita de não ranquear ou comparar empregadores.

---

## Próximas Evoluções

- Avaliação automatizada com LLM-as-judge (um modelo avalia as respostas do outro)
- Teste de consistência: mesma pergunta feita 5 vezes deve ter respostas equivalentes
- Rastreamento de taxa de hallucination com base expandida (50+ registros)
