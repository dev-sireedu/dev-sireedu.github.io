---
title: "Modularidade"
permalink: /dev/modularidade/
excerpt: "Modularidade do código"
last_modified_at: 2025-01-25T08:48:05-04:00
---

Como ilustrado na figura abaixo, a organização dos componentes das páginas da aplicação segue uma abordagem modular. Cada componente de página é autossuficiente e contém todos os recursos necessários para sua funcionalidade.

![modulos](/assets/images/code2.png)

A seguir estão os principais pontos dessa organização:

1. index.jsx: arquivo principal do diretório, responsável por estruturar e renderizar a lógica do componente.

2. styles.css: arquivo dedicado à estilização da página ou componente. Ele mantém os estilos isolados e locais, evitando interferências com outros componentes e facilitando a manutenção.

3. Subcomponentes: em cada diretório, podem existir componentes específicos que representam partes menores da página principal.

4. Hooks específicos: inclusão de um diretório hooks dentro das páginas permite encapsular lógicas reutilizáveis específicas da funcionalidade.