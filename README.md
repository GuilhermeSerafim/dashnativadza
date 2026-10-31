# Dashboard de projetos e tarefas

Este repositório é um fork da base identificada como **ClickUpClonemaster**, com referências de origem v0/Vercel ao final.

## Escopo do código

Dashboard de projetos e tarefas com Next.js 14, React 18 e TypeScript, identificado como `clickup-clone` no `package.json`. A página `app/dashboard/page.tsx` consulta tarefas, projetos e usuários pelo cliente Supabase, calcula contagens a partir das respostas e mantém atividades recentes em localStorage. Esses números representam os dados da interface.

Há também `app/dashboard/actions.ts`, com validação de título/espaço/prioridade e consulta de usuário autenticado antes da inserção de tarefa. A página cliente e essa action usam conjuntos diferentes de campos (`project_id`/`assigned_to` e `space_id`/`priority`); a compatibilidade depende do schema configurado. O isolamento dos dados entre usuários depende das permissões e políticas do banco, além da autenticação.

## Ambiente e limites

O `package.json` contém scripts `dev`, `build`, `start`, `lint`, `db:check` e `db:setup`. Os dois últimos chamam rotinas de banco e podem produzir efeitos no ambiente configurado. Antes de reproduzir, prepare um banco de desenvolvimento e confira os clientes, schema e permissões.

O repositório também inclui código em `server/src`, scripts SQL e arquivos de testes de integração. A relação entre esses componentes e o fluxo Next.js requer configuração do ambiente; eles não compõem, por si só, um procedimento único de instalação.

## Referências de origem — ClickUpClonemaster

- [v0.dev](https://v0.dev), plataforma indicada na documentação de origem.
- [Projeto de origem no v0](https://v0.dev/chat/projects/vlT5MzBczpP).
- [Painel Vercel de origem, no namespace rafa07roy](https://vercel.com/rafa07roy-3881s-projects/v0-click-up-clonemaster).

Quando configurada, a integração v0 pode sincronizar alterações com o repositório associado e o Vercel pode publicar suas novas versões. Esse fluxo depende das integrações do projeto associado; um fork precisa de configuração própria. O link Vercel acima aponta para um painel de implantação.
