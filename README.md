# clone-tabnews

Clone do [TabNews](https://www.tabnews.com.br), desenvolvido durante o [curso.dev](https://curso.dev), com foco em back-end, banco de dados, testes automatizados e boas práticas de desenvolvimento.

🔗 **Acesse:** https://clone-tabnews-five-tau-41.vercel.app

## Tecnologias

- **Next.js** e **Node.js**: aplicação web e API
- **PostgreSQL**: banco de dados, rodando em container com **Docker Compose**
- **node-pg-migrate**: migrations para versionar a estrutura do banco
- **Jest**: testes automatizados
- **GitHub Actions**: integração contínua (CI)
- **ESLint** e **Prettier**: padronização e qualidade do código
- **Husky**, **Commitlint** e **Commitizen**: commits no padrão Conventional Commits
- **Vercel**: deploy contínuo

## Funcionalidades

- `GET /api/v1/status`: retorna a data da consulta e informações do PostgreSQL (versão, limite de conexões e conexões abertas)
- `GET /api/v1/migrations`: lista as migrations pendentes, sem executá-las (dry run)
- `POST /api/v1/migrations`: executa as migrations pendentes (retorna `201` quando alguma é aplicada)

## Como rodar localmente

### Pré-requisitos

- [Node.js](https://nodejs.org) (versão definida no arquivo `.nvmrc`)
- [Docker](https://www.docker.com) com Docker Compose

### Passo a passo

```bash
# Clone o repositório
git clone https://github.com/Kelventz/clone-tabnews.git
cd clone-tabnews

# Instale as dependências
npm install

# Suba o banco, rode as migrations e inicie o servidor
npm run dev
```

A aplicação fica disponível em `http://localhost:3000`.

## Testes

```bash
# Roda todos os testes (sobe os serviços automaticamente)
npm test

# Roda os testes em modo observação
npm run test:watch
```

## Scripts úteis

| Comando                            | O que faz                                            |
| ---------------------------------- | ---------------------------------------------------- |
| `npm run services:up`              | Sobe o banco de dados no Docker                      |
| `npm run services:stop`            | Para os containers                                   |
| `npm run services:down`            | Remove os containers                                 |
| `npm run migrations:create <nome>` | Cria uma nova migration                              |
| `npm run migrations:up`            | Executa as migrations pendentes                      |
| `npm run lint:eslint:check`        | Verifica o código com ESLint                         |
| `npm run lint:prettier:check`      | Verifica a formatação                                |
| `npm run lint:prettier:fix`        | Corrige a formatação                                 |
| `npm run commit`                   | Cria um commit guiado no padrão Conventional Commits |

## Estrutura do projeto

```
├── .github/workflows   # Pipelines de CI
├── infra               # Docker Compose, migrations e scripts de infraestrutura
├── pages               # Páginas e rotas da API (Next.js)
└── tests               # Testes automatizados
```

## O que aprendi

- Configurar um ambiente de desenvolvimento com banco de dados em Docker
- Versionar a estrutura do banco com migrations
- Escrever testes de integração para a API
- Automatizar a verificação de código com CI no GitHub Actions
- Padronizar commits e manter um histórico organizado

## Autor

**Kelven da Silva Cunha**
[LinkedIn](https://www.linkedin.com/in/kelvencunha14) · [GitHub](https://github.com/Kelventz)
