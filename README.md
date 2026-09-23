# Agenda de Estudos

Miniaplicação desenvolvida com **Vue 3** e **Vue Router** para a atividade de fixação da unidade curricular **Frameworks Front End**, do curso de Análise e Desenvolvimento de Sistemas (Faculdade de Tecnologia SENAI Félix Guisard).

A aplicação permite organizar as tarefas de estudo do curso: o usuário digita uma tarefa, adiciona à lista e acompanha tudo em uma tela dedicada.

**Autor:** SEU NOME AQUI
**Professor:** Wesley Fioreze

## Links

- Projeto executável (StackBlitz): https://stackblitz.com/github/phenrique2407/AgendaEstudos
- Repositório: https://github.com/phenrique2407/AgendaEstudos

## Funcionalidades

- Duas telas conectadas por rotas, com navegação sem recarregar a página.
- **Tela inicial (`/`)**: título, nome do autor, frase sobre a finalidade da aplicação e link para a tela de tarefas.
- **Tela de tarefas (`/tarefas`)**: campo de texto ligado por `v-model`, botão **Adicionar** e lista renderizada com `v-for`.
- Tarefas vazias (ou só com espaços) não são adicionadas.
- Após adicionar, o campo de texto é limpo.
- Também é possível adicionar pressionando **Enter**.

## Capturas de tela

**Tela inicial (`/`)**

![Tela inicial da Agenda de Estudos](assets/pagina-home.png)

**Tela de tarefas (`/tarefas`)**

![Tela de tarefas com itens adicionados](assets/pagina-tarefas.png)

## Tecnologias

- [Vue 3](https://vuejs.org/) (Composition API com `<script setup>`)
- [Vue Router 4](https://router.vuejs.org/)
- [Vite](https://vitejs.dev/)

## Rotas

| Caminho    | Componente        | Descrição                              |
| ---------- | ----------------- | -------------------------------------- |
| `/`        | `HomeView.vue`    | Apresentação da aplicação              |
| `/tarefas` | `TarefasView.vue` | Cadastro e listagem de tarefas         |

## Estrutura do projeto

```
agenda-de-estudos/
├── index.html
├── package.json
├── vite.config.js
└── src/
    ├── main.js              # Cria o app e registra o router
    ├── App.vue              # Contém o <RouterView />
    ├── router/
    │   └── index.js         # Definição das rotas
    └── views/
        ├── HomeView.vue     # Tela inicial
        └── TarefasView.vue  # Tela de tarefas
```

## Conceitos de Vue utilizados

- **`v-model` (com `.trim`)**: sincroniza o campo de texto com o estado `novaTarefa`.
- **`v-for` com `:key`**: renderiza a lista de tarefas com identificação única de cada item.
- **`v-if`**: exibe uma mensagem quando não há tarefas.
- **`ref`**: estado reativo para o texto digitado e para a lista de tarefas.
- **`RouterLink` e `RouterView`**: navegação entre telas e região onde o componente da rota atual é exibido.

## Como executar localmente

Pré-requisito: [Node.js](https://nodejs.org/) instalado.

```bash
# clonar o repositório
git clone https://github.com/phenrique2407/AgendaEstudos.git
cd AgendaEstudos

# instalar as dependências
npm install

# iniciar o servidor de desenvolvimento
npm run dev
```

Depois, acesse o endereço exibido no terminal (normalmente `http://localhost:5173`).

## Ambiente de desenvolvimento

O projeto foi desenvolvido no **GitHub Codespaces** (VS Code no navegador) e publicado em repositório público no GitHub, por isso a execução online é feita pelo StackBlitz, que abre o repositório diretamente e não depende de conta.

## Observação sobre as rotas

O router usa `createWebHistory()`, que gera URLs limpas como `/tarefas`, sem o `#`. Caso o ambiente online apresente erro ao recarregar diretamente uma rota, basta trocar por `createWebHashHistory()` em `src/router/index.js`.
