# Scrum-Estoque

Projeto Java independente, extraído da NOXBO e preparado para revisão. A interface e as regras originais foram preservadas. Não houve publicação ou deploy desta candidata.

Demonstração local em Java 17/Maven/TeaVM 0.16.0, sem servidor, usuários ou dados reais. Não é um backend de estoque multiusuário.

## Compilar e testar

Instale Node.js 24 e JDK 17 e Maven 3.10.0. Execute `node scripts/build.mjs`. O script executa os testes e gera dist/ e hashes em artifacts/. `--offline` usa dependências já obtidas. `python3 scripts/security_scan.py --history` verifica os arquivos selecionados e histórico alcançável por padrões limitados.

MAVEN_BIN, JAVA_BIN, MAVEN_LOCAL_REPOSITORY e MAVEN_SETTINGS permitem configurar sua própria instalação/cache. Não há leitura ou conversão automática de credenciais de proxy. Os testes Java têm main próprio e são invocados explicitamente pelo script; mvn package sozinho não executa todas as asserções.

Sirva dist/ em servidor estático local para revisar a interface; abrir HTML por file:// pode impedir módulos. A aplicação não exige serviços externos. A CI está preparada, mas não foi executada no GitHub. As fontes tipográficas e licenças estão incluídas.

Leia SECURITY.md, INCIDENT_RESPONSE.md e docs/. Não há licença da aplicação escolhida automaticamente; as licenças de terceiros não concedem uma licença ao código do proprietário.

## Portabilidade e integridade

Revisão local de 20/10/2026: `.gitattributes` fixa LF nos arquivos de texto autorais e mantém os binários opacos. As licenças OFL de terceiros usam `-text` para preservar exatamente seus bytes e quebras de linha originais. Os hashes verificam os bytes reais; uma divergência não é ignorada nem normalizada para parecer válida. Os manifestos de saída usam `/` nos caminhos em todos os sistemas.

A CI possui matriz Linux/Windows preparada, com Actions fixadas em commits e checkout sem persistência de credenciais. Nenhum resultado remoto é presumido. Não há deploy no workflow.

No Windows, defina `MAVEN_HOME` para a pasta da distribuição Maven e mantenha `java.exe` no PATH (ou defina `JAVA_BIN`). O script usa o launcher Java Classworlds oficial, evitando shell e problemas com `.cmd`, espaços e caracteres especiais. Em Linux, `MAVEN_HOME` também pode ser usado; sem ele, `MAVEN_BIN` seleciona um executável Maven. O launcher direto não interpreta `MAVEN_OPTS`, `MAVEN_ARGS` ou opções de shell. Não coloque senhas nessas variáveis nem em arquivos versionados.

O launcher foi usado em um build Linux real e seus argumentos Windows foram testados; isso não equivale a um build nativo Windows. A CI Windows está preparada para localizar a instalação do Maven no runner.

Saída estática: `dist/index.html`, módulo Java/TeaVM, interface, fontes e avisos de terceiros. Esses arquivos são gerados e entregues separadamente no pacote de revisão; Maven, JARs de build, caches e `target/` não entram nas fontes a publicar.

Os dados ficam somente no navegador. Abas concorrentes possuem proteção contra sobrescrita, mas não existe banco compartilhado, autenticação ou sincronização entre dispositivos.

## Executar a interface local

Depois do build, inicie um servidor estático no diretório de saída, por exemplo:

```sh
python3 -m http.server 8080 --directory dist
```

No Windows com Python Launcher, use `py -m http.server 8080 --directory dist`. Abra `http://localhost:8080/`. Esses comandos são para a sua máquina; não iniciam hospedagem pública, não requerem conta e não enviam dados para a NOXBO. O Python também executa o guard de exposição; ele não é necessário ao visitante do app.
