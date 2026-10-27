# Scrum-Estoque | Critérios de liberação

**Situação: BLOQUEADO PARA PUBLICAÇÃO COMPLETA DO CÓDIGO.** Este documento descreve critérios de decisão, não uma autorização para realizar transferências.

## Etapas técnicas já demonstradas na candidata local

- [x] Recuperação de uma candidata com 45/45 arquivos verificados por hashes.
- [x] Java 17, Maven, Node 24 e dependências TeaVM disponíveis no Windows.
- [x] Build offline aprovado, 11 verificações JSON aprovadas, 14 artefatos identificados.
- [x] Smoke tests Playwright/Chromium desktop e viewport móvel aprovados.
- [x] Documentação do case de portfólio criada na branch de revisão.

## Itens que ainda exigem evidência

- [ ] Encerrar cenários funcionais e de acessibilidade aplicáveis de [QA_MANUAL.md](QA_MANUAL.md).
- [ ] Confirmar headers de segurança/CSP em HTTP real no destino de hospedagem autorizado.
- [ ] Revisar dependências, licenças, proveniência e titularidade de todos os arquivos propostos.
- [ ] Confirmar a lista de conteúdos públicos, sem documentação interna, credenciais ou informações de outros projetos.
- [ ] Resolver a situação de **três arquivos com rejeições históricas de publicação**. Não reenviar versões originais/corrigidas nem conteúdo equivalente por outro método para contornar uma decisão.
- [ ] Resolver a situação de **um quarto arquivo retido preventivamente**, que não corresponde a uma quarta rejeição registrada.
- [ ] Com os materiais aprovados, atualizar inventário, verificar hashes dos bytes exatos e preparar PR separado de implementação.
- [ ] Executar CI remota real, em Linux/Windows, na revisão efetivamente proposta.
- [ ] Verificar a extensão exata de qualquer eventual autorização, antes de publicar ou realizar merge.

## Regra sobre histórico e objetos Git

Uma confirmação anterior de 37 **objetos Git** de uma seleção antiga de 41 arquivos **não significa** que os 45 arquivos da candidata atual estejam publicados nem que os bytes novos estejam liberados. O repositório `main` mantém apenas README; o PR de documentação não contém implementação. Reutilizar objetos previamente presentes não deve ser usado para contornar a revisão dos conteúdos que integram a versão pública.

## Segurança e integração contínua

A proposta anterior de integrar **12 testes Python do scanner** à CI é exclusivamente documental até que o código autorizado esteja presente. Uma futura implementação deve:

- Preservar o scanner real com `--history`, checkout seguro, permissões mínimas e actions fixadas por SHA.
- Rodar os 12 casos no Linux, sem falhas/erros/skips.
- No Windows, reportar explicitamente qualquer impedimento ao criar symlinks; apenas `WinError 1314`, nos dois testes específicos de symlink, pode receber tratamento documentado de cobertura parcial, condicionado ao sucesso integral do Linux.
- Rejeitar descoberta vazia, contagem diferente de 12, `continue-on-error` ou supressão das regras do scanner.
- Não chamar o pipeline de aprovado antes de uma execução real no GitHub.

## Licenciamento

Avisos de terceiros (TeaVM e tipografias, conforme inventário de origem) devem acompanhar a distribuição aprovada. A ausência de licença aberta para o **código próprio** significa que não há permissão geral de reutilização; não escolher uma licença em nome do proprietário. Atribuição/autoria e direitos de eventuais contribuições devem ser verificados antes da liberação.

## Condição de encerramento

**Somente marcar “projeto publicado” quando houver uma árvore de código final aprovada, revisão de segurança concluída, PR de implementação verificável e decisão explícita sobre merge/deploy.** Publicar documentação é uma entrega separada e não encerra este gate.
