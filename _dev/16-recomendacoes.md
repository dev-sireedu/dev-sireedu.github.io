---
title: "Recomendações"
permalink: /dev/recomendacoes/
excerpt: "Página de Recomendações"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O diretório Recommendation possui 4 componentes individuais. Os componentes MA, ME e PE renderizam, respectivamente, as telas de Recomendações de Materiais de Apoio, Metodologias de Ensino e Objetos Educacionais. O componente RecommendationCard, renderiza os cartões de recomendação.

![modulos](/assets/images/code15.png)

O trecho de código ilustrado no código mostra a renderização do componente Recommendation para os produtos recomendados.

```jsx
const Recommendation = () => {
    const { recommendationId } = useParams();
    const { role } = JSON.parse(localStorage.getItem(SESSION_STORAGE_KEY));

    return (
        <div className="recommendation">
            <PageTitleUpdater title={"Recomendações"} />
            {recommendationId && (recommendationId === EDUCATIONAL_PRODUCTS) &&
                <div>
                    <PE role={role}/>
                </div>
            }

            {recommendationId && (recommendationId === METHODOLOGY) &&
                <div>
                    <ME role={role}/>
                </div>
            }

            {recommendationId && (recommendationId === SUPPORT_MATERIALS) &&
                <div>
                    <MA />
                </div>
            }
        </div>
    );
}

export default Recommendation; 
```

A tela de Objetos Educacionais apresenta recomendações personalizadas baseadas nos estilos de aprendizagem e inteligências múltiplas identificadas a partir dos questionários respondidos. As informações são exibidas em forma de cartões interativos, que são organizados em duas categorias principais: Produtos Recomendados e Mais Objetos Educacionais. Na visão do aluno, cada cartão contém o título do produto educacional, uma descrição detalhada, e a relevância do produto, que é determinada com base nos resultados dos questionários individuais.