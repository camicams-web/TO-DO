# Clareza — Lista de tarefas

Projeto acadêmico desenvolvido para o **SENAI**, com o objetivo de criar uma aplicação web simples, intuitiva e responsiva para organização de tarefas, prazos e metas pessoais.

O sistema foi desenvolvido com tecnologias web fundamentais — HTML, CSS e JavaScript puro — para demonstrar conhecimentos de estruturação de páginas, estilização, interação com o usuário, manipulação do DOM, armazenamento local e integração com serviços externos.

## Objetivo do projeto

O Clareza foi pensado para ajudar o usuário a transformar objetivos maiores em pequenas ações práticas. A aplicação reúne tarefas do dia, prazos, duração estimada, metas relacionadas e um plano sequencial em uma única interface.

Além de funcionar como uma lista de tarefas, o projeto busca aplicar princípios de organização, clareza visual, acessibilidade e experiência do usuário.

## Funcionalidades

### Gerenciamento de tarefas

- Adicionar novas tarefas.
- Informar prazo, duração e meta relacionada.
- Marcar tarefas como concluídas ou reabrir tarefas já concluídas.
- Excluir tarefas individualmente.
- Limpar todas as tarefas concluídas.
- Reordenar tarefas por arrastar e soltar.
- Exibir o total de tarefas e o percentual de conclusão.

### Busca e filtros

- Buscar tarefas pelo texto digitado.
- Exibir todas as tarefas.
- Filtrar somente tarefas pendentes.
- Filtrar somente tarefas concluídas.
- Exibir uma mensagem orientativa quando nenhum resultado é encontrado.

### Calendário

- Visualizar tarefas que possuem prazo em um calendário mensal.
- Navegar para o mês anterior e para o mês seguinte.
- Voltar rapidamente para o mês atual.
- Destacar o dia atual.
- Identificar tarefas concluídas dentro do calendário.

### Organização por etapas

A seção de pensamento sequencial permite criar um objetivo e dividi-lo em várias etapas:

- Definir um objetivo principal.
- Informar uma etapa por linha.
- Usar um roteiro básico como modelo inicial.
- Avançar e voltar entre as etapas.
- Marcar cada etapa como concluída.
- Acompanhar o progresso do plano.
- Salvar o plano para continuar depois.

### Integração com Zapier

A aplicação possui uma área de automatizações que permite conectar um webhook do Zapier. Com essa integração, eventos da aplicação podem iniciar ações em outras ferramentas, como Gmail, Slack ou Trello.

Eventos previstos:

- `task.created` — nova tarefa criada.
- `task.completed` — tarefa concluída.
- `task.reopened` — tarefa reaberta.
- `task.deleted` — tarefa excluída.
- `sequential.plan_created` — novo plano criado.
- `sequential.step_completed` — etapa de um plano concluída.

Para configurar:

1. Crie um Zap no Zapier.
2. Escolha **Webhooks by Zapier**.
3. Selecione o evento **Catch Hook**.
4. Copie a URL de webhook fornecida pelo Zapier.
5. Cole a URL na seção **Automatizações** do Clareza.
6. Salve a conexão.

A aplicação valida se o endereço começa com `https://` antes de salvar a configuração.

## Processo de desenvolvimento

O desenvolvimento do projeto foi organizado nas seguintes etapas:

1. **Levantamento da proposta:** definição do problema e das necessidades principais de uma lista de tarefas.
2. **Planejamento da interface:** organização das áreas de marca, introdução, progresso, calendário, formulário, filtros, tarefas, planos e automatizações.
3. **Construção da estrutura:** criação da página com HTML semântico, formulários, botões, listas, calendário e áreas de status.
4. **Desenvolvimento visual:** aplicação de cores, espaçamentos, cartões, tipografia, estados de interação e layout responsivo com CSS.
5. **Implementação da lógica:** criação, edição de estado, conclusão, exclusão, busca, filtros, ordenação e atualização dinâmica da interface com JavaScript.
6. **Persistência local:** uso do `localStorage` para manter tarefas, planos e webhook salvos no navegador.
7. **Integração externa:** implementação de envio de eventos para um webhook do Zapier usando `fetch`.
8. **Acessibilidade e usabilidade:** inclusão de rótulos, textos alternativos, mensagens de status, navegação por botões e estados visuais compreensíveis.
9. **Responsividade:** adaptação da interface para telas menores, incluindo celulares e tablets.
10. **Verificação final:** conferência da estrutura dos arquivos, funcionamento do JavaScript e coerência entre os recursos documentados e a aplicação.

## MCPs e ferramentas utilizadas no desenvolvimento

Durante o desenvolvimento assistido, foram utilizados recursos baseados em **MCP (Model Context Protocol)** para permitir que o agente trabalhasse de forma controlada no ambiente do projeto.

### Recursos identificados

- **MCP (Model Context Protocol):** comunicação controlada com o ambiente de desenvolvimento.
- **Sequential Thinking:** organização do raciocínio e decomposição do trabalho em etapas.
- **Page Agent:** apoio à interação e à verificação da interface no navegador.

O **Zapier Webhooks** também foi utilizado no projeto, mas como integração da aplicação, e não como MCP.

Esses recursos foram utilizados para:

- Inspecionar os arquivos existentes no workspace.
- Identificar a estrutura e os recursos já implementados no `index.html`.
- Localizar títulos, formulários, funções, eventos e integrações presentes no código.
- Criar e atualizar o arquivo `README.md`.
- Verificar se o README foi criado corretamente no diretório do projeto.
- Apoiar a revisão da documentação e a validação das informações descritas.

O uso de MCP não substitui o código da aplicação. Ele serviu como uma camada de comunicação segura entre o agente e o ambiente de desenvolvimento, ajudando na leitura, organização, documentação e verificação do projeto.

## Tecnologias utilizadas

- **HTML5:** estrutura semântica da aplicação.
- **CSS3:** layout, identidade visual, animações e responsividade.
- **JavaScript:** regras de negócio, eventos, filtros, calendário e atualização da interface.
- **DOM API:** interação com elementos da página.
- **`localStorage`:** persistência local de tarefas, planos e configurações.
- **Fetch API:** envio de eventos para o webhook do Zapier.
- **Zapier Webhooks:** integração opcional com outros serviços.
- **MCP:** apoio ao processo de inspeção, desenvolvimento e documentação no ambiente de trabalho.

## Como executar

O projeto é estático e não exige instalação de dependências ou etapa de compilação.

### Opção 1: abrir diretamente

Abra o arquivo [`index.html`](./index.html) em um navegador moderno.

### Opção 2: usar um servidor local

Na pasta do projeto, execute:

```bash
python -m http.server 8000
```

Depois, acesse:

```text
http://localhost:8000
```

## Armazenamento e privacidade

As tarefas, os planos sequenciais e a configuração do webhook são armazenados localmente no navegador por meio de `localStorage`.

Isso significa que:

- Os dados ficam vinculados ao navegador e ao dispositivo utilizados.
- Os dados não são sincronizados automaticamente entre dispositivos.
- Limpar os dados do navegador pode apagar as informações salvas.
- O webhook só é utilizado quando o usuário configura uma URL do Zapier.

## Estrutura do projeto

```text
.
├── index.html   # Página, estilos e lógica principal da aplicação
└── README.md    # Documentação do projeto
```

## Possíveis melhorias futuras

- Separar HTML, CSS e JavaScript em arquivos independentes.
- Adicionar testes automatizados.
- Criar autenticação de usuários.
- Implementar banco de dados para sincronização entre dispositivos.
- Adicionar categorias, prioridades e etiquetas.
- Permitir edição completa de tarefas existentes.
- Criar modo escuro.
- Adicionar exportação e importação de tarefas.
- Melhorar a configuração de múltiplas automações do Zapier.

## Considerações finais

O Clareza representa a aplicação prática de conceitos de desenvolvimento web estudados no contexto do **SENAI**, combinando interface, lógica de programação, armazenamento de dados no navegador, integração com serviços externos e documentação técnica.

## Licença

Este projeto foi desenvolvido para fins acadêmicos e ainda não possui uma licença de software definida.
