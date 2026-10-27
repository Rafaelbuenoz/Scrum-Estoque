# Scrum-Estoque | Case de portfólio

**Estado:** documentação de apresentação. A versão completa do código ainda não foi publicada neste repositório.

## Visão geral

Aplicação demonstrativa de gestão de estoque e acompanhamento de atividades Scrum, construída para estudo de regras de negócio, persistência local, interface web e testes automatizados.

## O que o projeto demonstra

- **Estoque:** interface de organização de itens, quantidades e validações de movimentação.
- **Scrum:** navegação por funcionalidades de acompanhamento e organização de trabalho.
- **Movimentações:** visualização do fluxo de alterações de estoque.
- **Tema:** alternância entre os modos claro e escuro, com preferência persistida.
- **Responsividade:** funcionamento básico verificado em desktop e viewport móvel no Chromium.

## Tecnologias

Java 17, Maven, TeaVM 0.16.0, JavaScript, HTML, CSS, Node.js 24 e Python para validação. O aplicativo foi projetado para execução estática e armazenamento no navegador. Não é um ERP em produção, não oferece contas de usuários nem sincronização multiusuário.

## Demonstração e evidências

Em 27/10/2026, uma candidata local de **45 arquivos** teve integridade conferida; o build Maven/TeaVM foi aprovado e gerou **14 artefatos**, com **11 verificações JSON** aprovadas. Smoke tests automatizados usando Playwright/Chromium passaram em desktop e viewport móvel, incluindo navegação básica de Scrum e movimentações, persistência do tema, ausência de overflow horizontal e ausência de erros de página detectados.

Esses resultados **não** substituem testes de acessibilidade, dispositivo físico ou verificação de cabeçalhos HTTP em hospedagem real.

## Publicação

A demonstração foi executada localmente. O código-fonte completo ainda está em revisão de conteúdo e segurança, e **não há link público de execução** para este projeto. Materiais de outro projeto privado não fazem parte desta apresentação.

> Este documento é um case de portfólio, não uma declaração de liberação do código.
