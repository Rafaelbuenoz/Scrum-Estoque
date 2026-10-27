# Scrum-Estoque | Evidências locais de validação

**Referência:** 27 de outubro de 2026  
**Escopo:** candidata local reconstruída e testada em ambiente Windows do proprietário. Este documento é um resumo redigido das saídas fornecidas pelo responsável; não inclui códigos, arquivos privados ou logs completos.

| Verificação | Evidência relatada | Limite |
| --- | --- | --- |
| Integridade da candidata | 45/45 arquivos coincidiram com o inventário antes e após a execução | Verifica bytes, não segurança semântica |
| Java/Node/Python | Java 17, compilador, Node 24 e Maven disponíveis | Apenas ambiente local |
| Maven/TeaVM | Build offline `APROVADO`, returncode 0 | Não é execução de CI no GitHub |
| Testes JSON | `json_11: true` | Suite integrada do validador |
| Artefatos | `generated_assets.ok: true`, 14 arquivos | Artefatos não enviados ao repositório |
| Navegador desktop | `browser.ok: true`, Scrum e movimentações, tema persistido, sem overflow horizontal nem erros de página relatados | Smoke test Chromium |
| Navegador móvel | `browser.ok: true` em `mobile-viewport`, mesmos campos aprovados | Emulação de viewport, não celular físico |
| Testes isolados adicionais | Evidências anteriores de 44 testes Java, 23 Node e 12 Python aprovados | Rodadas distintas, não substituem CI completa |

## O que permanece aberto

- Exercícios manuais completos de criação, edição, remoção, importação/exportação e acessibilidade.
- Cabeçalhos HTTP/CSP reais em hospedagem.
- Integração dos testes Python à CI remota e execução de pipeline Linux/Windows.
- Revisão de dependências e de avisos de licença; avaliação do Guava 20.0 no contexto de *build*.
- Aprovação da seleção pública final. A documentação de validação não remove restrições de publicação anteriormente registradas.

## Condição para disponibilizar o código

O repositório público deve receber somente uma seleção de arquivos com autorização de publicação e auditoria de segredos, licenças e histórico. **Nenhuma pendência ou restrição deve ser omitida** para fabricar um PR aprovado.

A `main` permanece intocada durante a preparação documental.
