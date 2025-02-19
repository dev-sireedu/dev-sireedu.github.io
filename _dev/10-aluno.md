---
title: "Tela do aluno"
permalink: /dev/aluno/
excerpt: "Página do Aluno"
last_modified_at: 2025-01-25T08:48:05-04:00
---

Novamente temos padrão adotado no projeto, com os dois arquivos principais index.jsx e styles.css, como ilustrado na Figura: O diretório Student contém o componente individual StudyBox, responsável por renderizar os cartões dos estudos de Estilos de Aprendizagem e Inteligências Múltiplas.

![modulos](/assets/images/code4.png)

Abaixo temos um trecho do código responsável por renderizar o componente StudyBox para os estudos de Estilos de Aprendizagem e Inteligências Múltiplas.

```jsx
        <div className="student">
            <PageTitleUpdater title={"Início"} />
            <div className="student-container">
                <div className="student-header">
                    <p className="primary-heading">Olá, <span>{ firstName }</span></p>
                </div>
                <div className="student-message-container">
                    <div className="student-text-section fade-in">
                        <p className="secondary-text">
                            Seja bem-vindo(a) ao Sistema de Recomendação de Objetos Educacionais e Metodologias de 
                            Ensino baseado na terorias das inteligências Múltiplas (SIREEDU).
                        </p>
                    </div>

                    <div className="student-text-section fade-in">
                        <p className="secondary-text">
                            Ao responder o questionário de estilos de aprendizagem de Honey-Alonso e o inventário das 
                            inteligências múltiplas de Armstrong, os resultados refletirão o que você pensa sobre si mesmo(a), 
                            e auxiliarão os docentes na escolha das ferramentas educacionais mais eficientes para o ensino dessa disciplina.
                        </p>
                    </div>

                    <div className="student-text-section fade-in">
                        <p className="secondary-text">
                            Aproveite as recomendações e o material de apoio (infográficos, vídeos, aúdios) para turbinar seu aprendizado. <br />
                            Foram organizados para você.
                        </p>
                    </div>
                </div>
                
                <div className="student-study-container">
                    {loading ? (
                        <div className="student-box-container">
                            <CardSkeleton />
                            <CardSkeleton />
                        </div>
                    ) : (    
                    <div className="student-box-container">
                        <StudyBox
                            title="Estilos de Aprendizagem"
                            backgroundColor="bg-ligth-blue"
                            answered={studiesAnswered && studiesAnswered[0] ? studiesAnswered[0] : false}
                            onClick={() => handleClick(EA_ID)}
                            result={results[0]}
                        />
                        <StudyBox
                            title="Inteligências Múltiplas"
                            backgroundColor="bg-red"
                            answered={studiesAnswered && studiesAnswered[1] ? studiesAnswered[1] : false}
                            onClick={() => handleClick(IM_ID)}
                            result={results[1]}
                            />
                    </div>
                    )}
                </div>
                {studiesAnswered && studiesAnswered[0] && studiesAnswered[1] &&
                <div>
                    <div className="student-text-section fade-in">
                        <p className="secondary-text">
                            Veja as recomendações listadas para o seu perfil.
                        </p>
                    </div>
                    <div>
                        <RecommendationGroup
                            recommendations={
                                [{  
                                    id: 1,
                                    title: 'Objetos Educacionais',
                                    color: 'ligth-blue-color',
                                    background: 'bg-ligth-blue',
                                    icon: <ImportantDevicesIcon />,
                                }]
                            }
                            navigate={navigate}
                        />
                    </div>
                </div>
                }
            </div>
        </div>
```