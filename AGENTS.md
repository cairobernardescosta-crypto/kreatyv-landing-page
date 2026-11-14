# AGENTS.md — Protocolo de proteção contra regressões e custo zero

Estas regras se aplicam a toda alteração neste repositório feita por Codex, agentes ou colaboradores. Respeite instruções específicas em arquivos existentes e não altere comportamento fora do escopo.

## Preservação obrigatória
1. Antes de editar, examine a estrutura, o histórico relevante, o estado do Git e os contratos usados pelos arquivos afetados.
2. Mapeie dependentes e efeitos colaterais: rotas, APIs, banco, migrações, autenticação, UI, integração, build e scripts.
3. Prefira edições mínimas; nunca apague funções, testes, dados, configurações ou integrações sem autorização explícita.
4. Adicione ou ajuste testes que reproduzam a mudança e protejam fluxos preexistentes. Priorize teste focal, depois suíte de regressão, lint, tipagem e build conforme os scripts reais do projeto.
5. Faça revisão de `git diff --check`, `git diff`, arquivos alterados e falhas preexistentes versus novas. Nunca afirme que testes passaram se não foram executados.
6. Em alterações visuais, compare fluxos existentes em desktop e mobile quando aplicável; em alterações de dados, use backup e migração reversível.
7. Para mudanças de alto risco, desenvolva em branch, apresente PR e só faça merge/deploy com validação explícita. Não alterar produção ou instalação local por padrão.
8. Reporte mudanças, possíveis impactos, comandos testados, resultados, bloqueios, riscos residuais e instruções de reversão.

## Política GitHub: somente recursos sem cobrança
- Priorize Git, branches, issues, pull requests e verificações locais. Não habilite recursos pagos, Copilot pago, Codespaces, runners maiores ou serviços externos com cobrança.
- GitHub Actions: caso necessário, use apenas runners padrão em repositório público, eventos `pull_request`/`push`, `permissions: contents: read`, `timeout-minutes` e `concurrency` com cancelamento. Sem tarefas agendadas frequentes, builds de releases automáticos ou armazenamento de artifacts sem justificativa.
- Em repositório privado, não presuma custo zero: workflows hospedados podem consumir cota e gerar cobranças; preferir validações locais até confirmar orçamento e bloqueio de gasto.
- Não alterar configurações de cobrança da conta, não solicitar créditos nem instalar ferramentas globais. Recursos grátis dependem do plano e das políticas atuais do GitHub.

## Definição de pronto
Alteração revisada, testes pertinentes realizados e resultados documentados; nenhum defeito novo conhecido; regressões e limitações declaradas. Nenhuma implementação está automaticamente aprovada por compilar.
