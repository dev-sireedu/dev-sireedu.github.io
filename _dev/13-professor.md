---
title: "Tela do professor"
permalink: /dev/professor/
excerpt: "Página do Professor"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O diretório Professor possui o componente individual DataTable, responsável por renderizar uma tabela interativa, que apresenta informações como o ano, semestre, turma e o tipo de estudo aplicado.

![modulos](/assets/images/code12.png)

```jsx
        <div className="professor">
            <PageTitleUpdater title={"Início"} />
            <div className="professor-container">
                <div className="professor-header">
                    <p className="primary-heading">Estudos Disponíveis</p>
                </div>
                <div className="about-section-text-container">
                    <div className="professor-text-section border-red-color fade-in">
                        <p className="secondary-text">
                            Apresentamos o resultado do levantamento do perfil 
                            cognitivo da sua turma de <span style={{ textTransform: 'capitalize' }}>{ classDescription }</span>. 
                            Os instrumentos utilizados foram o questionário de estilos de aprendizagem de Honey-Alonso e o 
                            inventário das inteligências múltiplas de Armstrong.
                        </p>
                    </div>
                </div>
                <div className="professor-datatable-section">
                {availableClassroomStudy && !loading ? (
                    <div>
                        <ExportCSV data={csvData} filename="estudos.csv" />
                        <DataTable rows={availableClassroomStudy} />
                    </div>
                ) : (
                    <Skeleton
                        variant="rectangular"
                        height={230}
                        style={{ borderRadius: 5 }}
                    />
                )}
                </div>
                <div>
                    <div className="professor-text-section border-orange-color fade-in">
                        <p className="secondary-text">
                            Veja as recomendações listadas para a sua turma.
                        </p>
                    </div>
                    <div>
                    {studiesAnswered && studiesAnswered[0] && studiesAnswered[1] ?
                    (
                        <RecommendationGroup
                            recommendations={
                                [
                                    {  
                                        id: 1,
                                        title: 'Objetos Educacionais',
                                        color: 'ligth-blue-color',
                                        background: 'bg-ligth-blue',
                                        icon: <ImportantDevicesIcon />,
                                    },
                                    {  
                                        id: 2,
                                        title: 'Metodologias de Ensino',
                                        color: 'primary-color',
                                        background: 'bg-primary-color',
                                        icon: <ExtensionIcon />,
                                    },
                                    {
                                        id: 3,
                                        title: 'Materiais de Apoio',
                                        color: 'red-color',
                                        background: 'bg-red',
                                        icon: <MenuBookIcon />,
                                    }
                                ]
                            }
                            navigate={navigate}
                        />
                    ) : (
                        <RecommendationGroup
                            recommendations={
                                [
                                    {
                                        id: 3,
                                        title: 'Materiais de Apoio',
                                        color: 'red-color',
                                        background: 'bg-red',
                                        icon: <MenuBookIcon />,
                                    }
                                ]
                            }
                            navigate={navigate}
                        />
                    )}
                    </div>
                </div>
            </div>
        </div>
```