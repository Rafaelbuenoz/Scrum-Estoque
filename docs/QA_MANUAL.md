# Scrum-Estoque | Plano de QA manual

**Estado: não executado integralmente.** Não marque resultados como aprovados sem registrar a execução na candidata local específica.

Preencher data, navegador/versão, sistema operacional, identificação do build e observações. Usar apenas dados fictícios; **não** subir gravações, exportações ou prints com conteúdo privado.

## Casos sugeridos

| ID | Cenário | Resultado esperado | Estado |
| --- | --- | --- | --- |
| QA-01 | Carregar o aplicativo por servidor `127.0.0.1` | Recursos carregados; interface utilizável; console sem erro funcional | Pendente |
| QA-02 | Navegar Estoque → Scrum → Movimentações | Navegação correta e estado consistente | Cobertura básica automatizada; manual pendente |
| QA-03 | Criar item válido com nome e quantidade fictícios | Item aparece com dados corretos | Pendente |
| QA-04 | Tentar quantidade negativa, inválida ou vazia | Operação rejeitada sem corromper estado | Pendente |
| QA-05 | Registrar movimentação de entrada | Quantidade e histórico refletem a operação | Pendente |
| QA-06 | Tentar saída maior que o saldo | Negativa com mensagem adequada e sem saldo incorreto | Pendente |
| QA-07 | Usar ações de Scrum disponíveis | Tarefas/estado atualizam corretamente | Pendente |
| QA-08 | Exportar backup em JSON com dados fictícios | Arquivo gerado contendo dados esperados, sem segredos | Pendente |
| QA-09 | Importar JSON válido em ambiente de teste | Dados restaurados conforme contrato; sem perda inesperada | Pendente |
| QA-10 | Importar JSON malformado ou incompatível | Erro seguro, estado anterior preservado | Pendente |
| QA-11 | Alternar tema, recarregar e usar nova aba | Preferência persistida; comportamento entre abas coerente | Persistência automatizada; teste ampliado pendente |
| QA-12 | Operar via Tab/Enter/Espaço e observar foco | Ordem de foco lógica, botões com nomes e operações acessíveis | Pendente |
| QA-13 | Verificar viewport estreita e móvel físico, quando disponível | Sem cortes, conteúdo essencial e ações acessíveis | Viewport em Chromium aprovado; físico pendente |
| QA-14 | Conferir aviso de terceiros e informações do projeto | Licenças/avisos presentes e adequados | Pendente |
| QA-15 | Verificar headers/CSP em uma hospedagem autorizada | Política efetivamente presente em HTTP; sem erros CSP inesperados | Pendente |

### Critérios de QA

- Para cada caso manual, registrar **Aprovado / Reprovado / Bloqueado**, data e evidência sintética.
- Falhas de validação, perda de dados, erros de JavaScript e regressões de teclado bloqueiam a aprovação funcional.
- Os 11 testes JSON automatizados **não substituem** os cenários manuais de importação/exportação.
- O teste de viewport móvel **não comprova** uso em aparelho físico.
- A declaração de CSP em arquivo `_headers` **não prova** que a hospedagem aplicará o cabeçalho.
- Não registrar uma revisão de segurança como concluída com base apenas em uma varredura por padrões.

Documentação e QA podem avançar sem publicar a candidata. O código permanecerá fora do repositório até liberação apropriada.
