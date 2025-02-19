---
title: "Estrutura do Código"
permalink: /dev/estrutura/
excerpt: "Principais elementos do código"
last_modified_at: 2025-01-25T08:48:05-04:00
---

A estrutura de pasta adotada foi planejada para seguir as boas práticas de organização de arquivos em React, visando modularidade e escalabilidade do projeto. A Figura abaixo apresenta os principais diretórios e sua distribuição:

![pastas](/assets/images/code1.png)

1. public: pasta destinada a arquivos estáticos que não são processados pelo React, como imagens, arquivos de configuração, favicon e index.html.

2. src: principal diretório do projeto onde está todo o código-fonte. Ele é dividido da seguinte forma:
- assets: usada para armazenar recursos como imagens, fontes e arquivos estáticos.
- components: contém conteúdos reutilizáveis em várias páginas.
- Context: responsável pelo gerenciamento de estado global utilizando a Context API do React.
- hooks: contém hooks personalizados, que encapsulam lógicas de funcionalidades específicas e reaproveitáveis em diversos componentes.
- pages: agrupa os componentes principais que representam as páginas do sistema. Cada pasta representa uma rota ou seção distinta da aplicação.
- routes: arquivos responsáveis por definir as rotas do sistema, conectando as páginas e navegando entre elas.
- services: contém funções para chamadas à API, abstraindo as requisições HTTP e organizando o consumo de dados.
- styles: centraliza as folhas de estilo globais, como o arquivo global-styles.css, garantindo a aplicação de estilos padronizados em toda a aplicação.

3. Arquivos principais na raiz:
- App.jsx: componente principal onde a aplicação é inicializada e outros componentes são renderizados.
- index.js: ponto de entrada da aplicação React. Aqui, o ReactDOM renderiza o componente App no DOM.
- .gitignore: define arquivos que não devem ser versionados no Git.
- package.json e package-lock.json: contêm as dependências e informações do projeto.
- README.md: arquivo de documentação com instruções sobre o projeto.