# Clareza — Lista de tarefas

Aplicação web responsiva para organizar tarefas, prazos e metas em um único espaço visual.

## Arquivos

- `index.html` — aplicação principal, com HTML, CSS e JavaScript em um único arquivo.
- `demo-agente.html` — versão demonstrativa com aviso de uso de IA e Page Agent.
- `evidencia-lista-tarefas.png` — evidência visual da aplicação.
- `evidencia-testes.png` — evidência dos testes realizados.
- `evidencia-testes-playwright.png` — evidência dos testes automatizados.
- `evidencia-testes-final.png` — evidência final da interface.

## Recursos

- Cadastro, conclusão, reabertura e exclusão de tarefas.
- Busca e filtros por status.
- Reordenação por arrastar e soltar.
- Prazo, duração e meta relacionada em cada tarefa.
- Calendário mensal com tarefas vinculadas às datas.
- Indicador visual de progresso.
- Pensamento sequencial com objetivo, etapas e acompanhamento do progresso.
- Persistência local usando `localStorage`.
- Interface responsiva para desktop e celular.
- Animações visuais com suporte a `prefers-reduced-motion`.

## Como executar

Não há dependências ou etapa de compilação. Abra `index.html` diretamente no navegador ou execute um servidor local na pasta do projeto:

```bash
python -m http.server 8000
```

Depois acesse:

```text
http://localhost:8000/index.html
```

## Integração com Zapier

O site envia eventos para um webhook configurado pelo usuário. Para conectar:

1. No Zapier, crie um Zap com `Webhooks by Zapier` e o gatilho `Catch Hook`.
2. Copie a URL fornecida pelo Zapier.
3. Cole a URL na área `Automatizações` do site.
4. Clique em `Salvar conexão`.

Eventos enviados:

- `task.created`
- `task.completed`
- `task.reopened`
- `task.deleted`
- `sequential.plan_created`
- `sequential.step_completed`

Cada evento inclui a origem (`Clareza`), os dados da tarefa ou plano e o horário de envio.

## Armazenamento

Os dados são salvos localmente no navegador do usuário:

- `clareza-tarefas-v1` — tarefas.
- `clareza-zapier-webhook-v1` — URL do webhook.
- `clareza-sequential-plan-v1` — plano sequencial.

Limpar os dados do site no navegador também remove essas informações.

## Validação

O JavaScript pode ser validado com:

```bash
node -e "const fs=require('fs'); const h=fs.readFileSync('index.html','utf8'); const s=h.split('<script>')[1].split('</script>')[0]; new Function(s); console.log('JavaScript OK');"
```

Os principais fluxos testados são criação de tarefas, filtros, conclusão, calendário, plano sequencial e envio de evento ao webhook do Zapier.
