---
title: "Resultados"
permalink: /dev/resultados/
excerpt: "Página de Resultados"
last_modified_at: 2025-01-25T08:48:05-04:00
---

A estrutura de arquivos Result contém 3 componentes individuais. O componente EAResult renderiza a tela de resultados de Estilos de Aprendizagem, IMResult renderiza a tela de resultados de Inteligências Múltiplas, e ResultBox renderiza os modelos de pontuação do estudante em cada estudo.

![modulos](/assets/images/code11.png)

Trecho do código responsável por renderizar os componentes EAResult e IMResult.

```jsx
        <div className="result">
            <PageTitleUpdater title={"Resultado"} />
            <div className="result-container">
                <div className="result-header">
                    <p className="primary-heading">Resultado</p>
                    <h2>{studyDescription ? studyDescription : ""}</h2>
                </div>
                <div className="result-content-container">
                    {studyId === "1" &&
                        <EAResult scores={scores}/>
                    }

                    {studyId === "2" &&
                        <IMResult scores={scores} />
                    }
                </div>
            </div>
        </div>
```