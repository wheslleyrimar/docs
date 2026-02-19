# Documentação do Projeto — Templates

Repositório de **templates de documentação** para padronizar features, APIs, decisões técnicas e boas práticas. Os templates são pensados para uso por **engenheiros** e **agentes/LLMs**, com estrutura consistente e instruções embutidas.

---

## Estrutura

```
docs/
└── project/
    └── templates/
        ├── tech/           # Documentação técnica
        │   ├── howto.md
        │   ├── feature.md
        │   ├── api-readme.md
        │   ├── api-endpoint.md
        │   └── adr.md
        └── best_practice/  # Boas práticas e workflows
            └── do_one_commit.md
```

---

## Templates técnicos (`tech/`)

| Template | Uso |
|----------|-----|
| **howto.md** | Guias passo a passo: objetivo, pré-condições, passos, validação e referências. Mantém foco procedural. |
| **feature.md** | Especificação de feature: resumo, contexto, escopo, arquitetura, riscos, rollback, monitoramento e referências. Inclui metadados (ticket, PR, esforço) e instruções para agentes. |
| **api-readme.md** | Índice da API de um domínio: propósito, base path e tabela de endpoints com links para os arquivos de cada endpoint. |
| **api-endpoint.md** | Documentação de um endpoint: método/path, code pointers, contrato (auth, request/response, status codes), cache, side effects, observabilidade e diagrama de sequência (Mermaid). |
| **adr.md** | Architecture Decision Record: contexto, decisão, opções consideradas, consequências e links para docs relacionados. Nome do arquivo: `YYYY-MM-DD--short-title.md`. |

---

## Boas práticas (`best_practice/`)

| Template | Uso |
|----------|-----|
| **do_one_commit.md** | Workflow para transformar vários commits em **um único commit** antes de abrir/mergear PR: atualizar `CHANGELOG.md`, soft reset, stage, commit com convenção `[VERB]: descrição` e force-push (pelo usuário). Inclui verbos permitidos e regras para a mensagem de commit. |

---

## Convenções gerais

- **Metadados**: tabelas no topo (data, donos, ticket, status, etc.).
- **Diagramas**: Mermaid (`sequenceDiagram` para fluxos de API, `flowchart` para alto nível).
- **Agentes**: comentários `<!-- AGENT: ... -->` em vários templates com instruções para preenchimento e descoberta.
- **Datas**: convenção `YYYY-MM-DD` e nomes de arquivo `YYYY-MM-DD--short-name.md` quando aplicável.

---

## Como usar

1. Copie o template adequado para o local do seu domínio/feature (ex.: `docs/project/features/`, `docs/project/api/`, `docs/project/decisions/`).
2. Substitua os placeholders (`{...}`) e preencha as seções conforme o contexto.
3. Para features e endpoints, prefira extrair dados de tickets/PRs e código em vez de inventar campos.
4. Mantenha ADRs curtos e focados em decisão; detalhes de implementação ficam nos docs de feature.

---

*Projeto: Fintech Dev — Aula 11*
