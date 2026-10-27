# Scrum-Estoque | Guia de demonstração local

> **Importante:** o código da aplicação não foi publicado neste repositório. Este guia só funciona com a candidata reconstruída e validada **no computador do proprietário**. Não baixe uma versão incompleta do GitHub esperando que ela compile.

## Pré-requisitos já validados no PC pessoal (27/10/2026)

- Projeto recuperado em `C:\Projetos\Scrum-Estoque` com 45/45 arquivos íntegros.
- JDK 17, Maven 3.10.0, Node.js 24 e Python disponíveis.
- Dependências Maven/TeaVM 0.16.0 já preparadas no cache local.
- Compilação offline e smoke tests de Chromium desktop/viewport móvel aprovados no ambiente testado.

## Abrir a versão real

No **PowerShell do seu computador pessoal**, após confirmar que o diretório existe:

```powershell
Set-Location "C:\Projetos\Scrum-Estoque"
$env:MAVEN_HOME = "$env:USERPROFILE\Documents\apache-maven-3.10.0"
node scripts/build.mjs --offline
py -3 -m http.server 8765 --bind 127.0.0.1 --directory dist
```

Abra `http://127.0.0.1:8765/`. Deixe o terminal do servidor aberto durante a demonstração; use **Ctrl+C** para encerrá-lo. O endereço **127.0.0.1** restringe o servidor ao próprio computador. O servidor estático local não equivale a hospedagem pública.

A compilação cria/atualiza saídas locais em `dist/` e artefatos de build. **Não altere, apague ou envie arquivos-fonte durante a demonstração.** Se a execução falhar, guarde o log em vez de modificar as verificações.

## Roteiro de apresentação (3–5 minutos)

1. **Contexto (30 s):** projeto demonstrativo para praticar regras de estoque, organização de tarefas Scrum e interface web.
2. **Estoque (60 s):** navegue pelos itens, apresente quantidades e limites de validação. Use apenas nomes e números fictícios.
3. **Movimentações (60 s):** percorra a interface e demonstre um fluxo de alteração quando disponível.
4. **Scrum (60 s):** mostre a organização de tarefas e como a navegação ajuda a acompanhar trabalho.
5. **Tema e responsividade (30 s):** alterne o tema, recarregue para verificar persistência e ajuste a largura do navegador.
6. **Engenharia (30 s):** explique Java 17 + TeaVM, build Maven e evidências de testes, sem afirmar que o sistema é um produto comercial.

## Dados e privacidade

- **Não utilize dados reais** de clientes, fornecedores, colaboradores ou empresas.
- Use produtos fictícios, por exemplo: `Item demonstração A`, `Item demonstração B`.
- Evite compartilhar imagens contendo favoritos, histórico, credenciais, extensões ou notificações pessoais.
- Os dados ficam no armazenamento do navegador; perfis e navegadores diferentes podem não compartilhar o mesmo estado. Não trate isso como sincronização em nuvem.
- Para limpar dados da demonstração, use os controles do próprio aplicativo ou as configurações do navegador, **após confirmar que não há dados que você deseje preservar**.

## O que foi comprovado e o que falta

Em 27/10/2026, o validador relatou `build.status: APROVADO`, `json_11: true`, `generated_assets.ok: true`, `browser.ok: true` e dois smoke tests aprovados (`desktop` e `mobile-viewport`). Esses testes cobriram navegação básica de Scrum e movimentações, persistência do tema, overflow horizontal e erros de página.

**Não foram declarados concluídos:** fluxos manuais completos de importação/exportação, acessibilidade por teclado/leitor de tela, dispositivo móvel físico, revisão visual detalhada e cabeçalhos HTTP reais de produção. Consulte [a checklist de QA](QA_MANUAL.md).

Nenhum conteúdo deste documento autoriza publicar os arquivos de código retidos em revisão.
