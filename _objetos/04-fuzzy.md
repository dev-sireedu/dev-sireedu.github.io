---
title: "Estilos de Aprendizagem"
permalink: /objetos/fuzzy/
excerpt: ""
last_modified_at: 2025-01-26T08:48:05-04:00
redirect_from:
  - /theme-setup/
toc: true
---

## Lógica Fuzzy
A Lógica Fuzzy, também conhecida como Lógica Nebulosa, surgiu a partir da teoria dos conjuntos, com o objetivo de flexibilizar a rigidez numérica da matemática clássica (Barros; Fernandes, 2019). Um sistema baseado na Lógica Fuzzy é estruturado em quatro módulos principais: o módulo de fuzzificação, que processa as entradas; a base de regras fuzzy, que define as regras do tipo "Se [entrada], então [saída]"; o método de inferência fuzzy, responsável pela lógica interna do sistema; e o processo de defuzzificação, que converte um conjunto fuzzy em um número real (Barros; Fernandes, 2019).

No campo da inteligência artificial, a Lógica Fuzzy aproxima-se do modo como os humanos lidam com incertezas, raciocínios aproximados e termos ambíguos. Essa técnica é particularmente adequada para a representação de situações do mundo real, onde as fronteiras entre pertencer ou não a um conjunto são graduais e não abruptas (Stopa, 2023).

## Sistemas baseados em regra Fuzzy

Um sistema baseado em regras fuzzy é composto por quatro etapas: fuzzificação, base de regras fuzzy, máquina de inferência fuzzy e defuzzificação (Silva, 2011). Na etapa de fuzzificação, as entradas são modeladas por meio de funções de pertinência que representam os conjuntos fuzzy envolvidos no processo (Silva, 2011). Na etapa seguinte, a base de regras fuzzy é composta por proposições linguísticas do tipo:

&npsb&npsb&npsb&npsb&npsb&npsb **Se** x1 é A1 e x2 é A2 e ... e ... xn é AN
&npsb&npsb&npsb&npsb&npsb&npsb **Então** u1 é B1 e u2 é B2 e... e ... un é BN

A máquina de inferência fuzzy processa essas proposições, gerando as saídas fuzzy a partir das entradas modeladas. Finalmente, na etapa de defuzzificação, o sistema converte os conjuntos fuzzy em valores reais, permitindo a tomada de decisões concretas (Silva, 2011).


## Métodos de Defuzzificação
O software utilizado para o desenvolvimento da lógica fuzzy oferece diferentes métodos de defuzzificação, cada um com suas particularidades. Dentre esses métodos, destacam-se o Centroid, o Bisector, o Middle of Maximum (MOM), o Smallest of Maximum (SOM) e o Largest of Maximum (LOM).

O método Centroid calcula o centro de gravidade do conjunto fuzzy ao longo do eixo x, representando a média ponderada dos valores possíveis. Já o método Bisector encontra a linha vertical que divide o conjunto fuzzy em duas sub-regiões de áreas iguais, muitas vezes coincidente com a linha do Centroid. O método Middle of Maximum (MOM) retorna o valor central do conjunto, enquanto o Smallest of Maximum (SOM) escolhe o menor valor encontrado no conjunto. Por fim, o Largest of Maximum (LOM) seleciona o maior valor possível dentro do conjunto fuzzy (MathWorks, 2024). A Figura abaixo ilustra a aplicação dos diferentes métodos de defuzzificação em um conjunto fuzzy.

![fuzzy](/assets/images/fuzzy.png)

Através da Figura, observa-se que o método SOM seleciona o menor valor correspondente à pertinência máxima, enquanto o MOM identifica o valor central desse intervalo. O método LOM, por sua vez, aponta o maior valor com pertinência máxima. O Centroid e o Bisector, embora não explicitamente visíveis na figura, coincidem com a média ponderada e a divisão exata das áreas sob o conjunto fuzzy, respectivamente. Desta forma, a Figura 1 exemplifica como cada método fornece uma saída diferente com base no mesmo conjunto fuzzy, refletindo as características distintas de cada abordagem.