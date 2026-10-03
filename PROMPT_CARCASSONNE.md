# Carcassonne — Etapa 1: estrutura simples do projeto

## Objetivo desta tarefa

Estamos começando um projeto universitário de Carcassonne, usando TypeScript para as classes e regras e Phaser para a interface.

Vamos desenvolver pouco a pouco. Nesta etapa, crie somente a estrutura inicial de pastas e os arquivos básicos. Não implemente funcionalidades e não avance para a próxima etapa sem meu pedido.

Esta versão substitui qualquer instrução anterior de criar uma estrutura mais complexa ou implementar o jogo inteiro.

## Antes de começar

- Confira e informe o caminho da pasta aberta atualmente. Trabalhe nessa pasta, sem usar caminhos antigos do histórico.
- Inspecione o que já existe e preserve os arquivos existentes.
- Consulte os PDFs e o diagrama em `docs/referencias`, caso estejam disponíveis. Se estiverem diretamente em `docs`, pode mantê-los ali.
- Use os anexos como referência do projeto futuro, não como autorização para implementar tudo agora.
- Se já existir código ou alguma estrutura diferente, não apague nem reorganize automaticamente: crie apenas o que estiver faltando e informe as diferenças.

## Estrutura desejada

Use uma organização simples, adequada a um trabalho de faculdade:

```text
Carcassonne/
├── src/
│   ├── main.ts
│   ├── jogo/
│   │   └── .gitkeep
│   ├── ia/
│   │   └── .gitkeep
│   └── telas/
│       └── .gitkeep
├── public/
│   └── assets/
│       └── .gitkeep
├── testes/
│   └── .gitkeep
├── docs/
│   └── referencias/
│       ├── carcassonne__completo.pdf
│       ├── Rfs.pdf
│       └── diagrama-classes.png
├── index.html
├── package.json
├── tsconfig.json
├── .gitignore
├── README.md
└── PROMPT_CARCASSONNE.md
```

`Carcassonne` representa a pasta atual do projeto, qualquer que seja seu nome. Não crie outra pasta Carcassonne dentro dela.

Preserve os documentos de referência que já existirem. Se algum anexo estiver ausente, informe isso; não crie um PDF ou imagem vazios para substituí-lo. A ausência dos anexos não impede criar esta estrutura básica.

O arquivo `.gitkeep` é apenas um arquivo vazio para preservar uma pasta vazia no Git. Não precisa inicializar um repositório agora.

## Responsabilidade de cada pasta

- `src/jogo`: futuramente terá as classes e regras, como Game, Board, Tile, Player, Meeple, construções, pontuação, enums e interfaces relacionados ao jogo. Os arquivos ficarão juntos, sem subdivisões por categoria.
- `src/ia`: futuramente terá as estratégias fácil e difícil do computador.
- `src/telas`: futuramente terá as telas e a interação com Phaser.
- `public/assets`: recursos visuais e sonoros, quando forem necessários.
- `testes`: testes das regras, criados junto com as futuras implementações.
- `docs`: documentos de referência do trabalho.

As regras do jogo deverão ser independentes da interface. Essa separação não exige outras camadas ou pastas nesta etapa.

## Arquivos básicos

Crie somente:

1. `src/main.ts`: um comentário indicando que será o ponto de entrada. Sem imports ou código executável.
2. `index.html`: HTML mínimo com idioma `pt-BR`, charset UTF-8, viewport e título `Carcassonne`. Corpo vazio, sem interface e sem carregar scripts.
3. `package.json`: JSON válido com nome `carcassonne-academico`, versão `0.1.0`, `private: true`, `type: "module"` e descrição breve. Sem dependências ou scripts nesta etapa.
4. `tsconfig.json`: configuração inicial com `target: "ES2022"`, `module: "ESNext"`, `moduleResolution: "Bundler"`, `lib: ["ES2022", "DOM"]`, `strict: true`, `noEmit: true` e `include: ["src/**/*.ts"]`.
5. `.gitignore`: ignorar `node_modules/`, `dist/`, `coverage/`, `*.log`, `.env` e `.env.*`, preservando eventual `.env.example`.
6. `README.md`: revisar e complementar o README inicial incluído no pacote, conforme a seção abaixo. Preserve as orientações úteis já existentes e ajuste qualquer informação ao estado real da pasta. Se ele não existir, crie-o.
7. Arquivos `.gitkeep` nas pastas vazias indicadas.

Preserve este `PROMPT_CARCASSONNE.md`. Não crie agora um arquivo para cada classe do diagrama: eles serão adicionados conforme implementarmos cada parte.

Registre no README, como decisões para etapas futuras, que o jogo incluirá meeple grande e usará a quantidade de meeples disponíveis antes da contagem final como critério de desempate. Não implemente essas regras agora.

## README do GitHub e manutenção da documentação

O README deve ser simples, em português, e servir aos integrantes que querem baixar o projeto, atualizar sua cópia, alterar o código ou jogar. O pacote inclui uma versão inicial; revise-a no projeto local. Ela não autoriza instalar dependências ou implementar funcionalidades nesta etapa.

Inclua ou mantenha:

- Descrição acadêmica do projeto, tecnologias e organização simples das pastas.
- Estado atual verdadeiro: nesta etapa há somente estrutura, sem jogo executável.
- Como baixar pela primeira vez com `git clone` e abrir a pasta no VS Code. Use a URL real do repositório se estiver configurada; caso contrário, deixe um placeholder claramente identificado, sem inventar usuário ou endereço.
- Como atualizar uma cópia clonada: conferir `git status` e usar `git pull --ff-only` na branch local que acompanha a remota. Explicar que a pasta extraída de um ZIP não tem necessariamente um repositório Git e que alterações locais precisam ser tratadas antes de atualizar.
- Ferramentas necessárias em cada etapa. Agora, Git para colaborar e um editor; Node.js/npm serão necessários quando a configuração de desenvolvimento for implementada. Mais adiante, informar as versões realmente adotadas.
- Como instalar dependências, desenvolver, testar, gerar build e jogar, somente quando esses recursos existirem. Na etapa inicial, marcar essas instruções como ainda não disponíveis, sem apresentar comandos futuros como se já funcionassem.

**Nas próximas tarefas deste projeto, quando eu solicitar mudanças de código ou configuração, atualize também o README se elas alterarem requisitos, comandos, controles, funcionalidades ou o modo de executar.** Esse cuidado documental não autoriza iniciar a próxima tarefa por conta própria.

Quando houver ambiente executável, documente os scripts reais do `package.json`, o gerenciador e lockfile usados, o endereço indicado pelo servidor e os controles implementados. Se usar npm com `package-lock.json`, explique `npm ci`; não recomendar esse comando enquanto o lockfile não existir. Nunca afirmar que comandos foram testados sem executá-los. Registre limitações reais e remova instruções obsoletas conforme o projeto avançar.

## Limites desta etapa

- Não criar classes, interfaces, enums, funções ou métodos, nem mesmo vazios.
- Não implementar tabuleiro, peças, turnos, meeples, pontuação ou IA.
- Não criar telas, cenas Phaser, estilos, imagens, sons ou animações.
- Não criar catálogo de peças, exemplos, mocks ou testes.
- Não criar outras pastas como domain, application, ports, services ou shared.
- Não instalar dependências, executar geradores de projeto, iniciar servidor ou gerar build e lockfile.
- Não fazer commits, criar repositório remoto ou publicar o projeto.
- Não executar automaticamente nenhuma etapa posterior.

## Verificação e encerramento

Confira a estrutura criada, a sintaxe dos arquivos JSON e a preservação dos arquivos preexistentes. Não instale ferramentas para essa conferência. Não afirme que o jogo, a compilação ou os testes funcionam: ainda não estarão implementados.

Ao terminar, informe o caminho utilizado, liste o que foi criado e explique brevemente as pastas principais. Aponte eventuais arquivos ausentes ou conflitos.

Pare assim que a estrutura estiver pronta e aguarde meu próximo pedido.
