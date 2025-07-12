# NLW Agents

Projeto desenvolvido durante a Next Level Week (NLW) Agents, um evento online da [Rocketseat](https://www.rocketseat.com.br/).

## Sobre o projeto

A aplicação funciona como uma plataforma de perguntas e respostas (Q&A) para salas de áudio. Os usuários podem criar salas, enviar perguntas e também transcrever trechos de áudio para texto, utilizando a IA do Google Gemini para gerar respostas automáticas com base no conteúdo transcrito.

<img src="web/public/home.png"/>
<img src="web/public/sala.png"/>
<img src="web/public/audio.png"/>

## Tecnologias

Este projeto é um monorepo e utiliza as seguintes tecnologias:

### **Backend**

-   **Node.js**: Ambiente de execução do servidor.
-   **Fastify**: Framework web de alta performance.
-   **TypeScript**: Superset do JavaScript que adiciona tipagem estática.
-   **Drizzle ORM**: ORM "headless" para interagir com o banco de dados.
-   **PostgreSQL (com pgvector)**: Banco de dados relacional com suporte para vetores.
-   **Zod**: Biblioteca para validação de esquemas e tipos.
-   **Docker**: Para gerenciamento de contêineres do banco de dados.
-   **Google Gemini**: API de inteligência artificial para geração de conteúdo.

### **Frontend**

-   **React**: Biblioteca para construção de interfaces de usuário.
-   **Vite**: Ferramenta de build e desenvolvimento rápido para projetos web modernos.
-   **TypeScript**: Linguagem de programação principal.
-   **Tailwind CSS**: Framework CSS utility-first para estilização.
-   **shadcn/ui**: Componentes de UI reusáveis construídos sobre Radix UI e Tailwind CSS.
-   **TanStack Query**: Para data fetching, cache e sincronização de estado do servidor.
-   **React Hook Form & Zod**: Para construção e validação de formulários.
-   **React Router**: Para gerenciamento de rotas na aplicação.

## Setup do Projeto

### **Pré-requisitos**

-   [Node.js](https://nodejs.org/en/) (v20 ou superior)
-   [Docker](https://www.docker.com/)

### **Backend**

1.  **Navegue até a pasta do servidor:**
    ```bash
    cd server
    ```

2.  **Instale as dependências:**
    ```bash
    npm install
    ```

3.  **Crie o arquivo de ambiente:**
    Crie um arquivo `.env` na raiz da pasta `server` e adicione as seguintes variáveis:

    ```env
    DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
    GEMINI_API_KEY=SUA_CHAVE_API_DO_GEMINI
    ```

    > Substitua `SUA_CHAVE_API_DO_GEMINI` pela sua chave de API do Google Gemini.

4.  **Inicie o banco de dados com Docker:**
    ```bash
    docker-compose up -d
    ```

5.  **Execute as migrations do banco de dados:**
    ```bash
    npm run db:migrate
    ```

6.  **Inicie o servidor de desenvolvimento:**
    ```bash
    npm run dev
    ```

    O servidor estará rodando em `http://localhost:3333`.

### **Frontend**

1.  **Navegue até a pasta do cliente web:**
    ```bash
    cd web
    ```

2.  **Instale as dependências:**
    ```bash
    npm install
    ```

3.  **Inicie a aplicação de desenvolvimento:**
    ```bash
    npm run dev
    ```

    A aplicação estará disponível em `http://localhost:5173`. 
