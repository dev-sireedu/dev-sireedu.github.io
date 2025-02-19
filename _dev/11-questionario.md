---
title: "Questionário"
permalink: /dev/questionario/
excerpt: "Página do Questionário"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O diretório Questions possui 5 componentes individuais. O componente Answered exibe ao usuário uma mensagem de questionário respondido. AnswersGroup renderiza o modelo de botões de respostas (Nunca se aplica a mim, Aplica-se raramente a mim, Aplica-se muitas vezes a mim, e Aplica-se sempre a mim). O componente LinearProgress refere-se a barra de progresso, que é incrementada a cada resposta do estudante. Por fim, os componentes Term e TermDialog são responsáveis por renderizar o Termo de Consentimento Livre e Esclarecido, que é exibido ao estudante antes da aplicação dos questionários.

![modulos](/assets/images/code9.png)

A Figura abaixo ilustra o modelo de questionário aplicado para os estudos de Estilos de Aprendizagem e Inteligências Múltiplas. Cada questão é apresentada com frases que permitem ao estudante refletir sobre suas preferências ou comportamentos. O questionário utiliza um formato de múltipla escolha, no qual o estudante pode optar por uma das seguintes alternativas: “Nunca se aplica a mim”, “Aplica-se raramente a mim”, “Aplica-se muitas vezes a mim”, e “Aplica-se sempre a mim”. Localizada na parte superior da tela, a barra de progresso exibe visualmente o avanço do estudante ao longo do questionário. A cada resposta selecionada, a barra é incrementada, indicando o progresso. Após o estudante selecionar uma resposta, a questão atual é substituída automaticamente pela próxima, mantendo a fluidez da experiência.

![modulos](/assets/images/code10.png)