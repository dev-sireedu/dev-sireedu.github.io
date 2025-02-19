---
title: "Relatório Sintético"
permalink: /dev/sintetico/
excerpt: "Página de Relatório Sintético"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O diretório Synthetic possui 3 componentes individuais. O componente DataTable é responsável por renderizar uma tabela, onde é exibida a média percentual de aderência dos estudantes em cada estilo ou inteligência avaliada. EASynthetic renderiza a página para o estudo de Estilos de Aprendizagem, e IMSynthetic renderiza a página para o estudo de Inteligências Múltiplas.

![modulos](/assets/images/code13.png)

O trecho de código ilustrado mostra a etapa em que os dados exibidos na página de relatório sintético são tratados para serem usados gráfico (setChartData), na exportação em CSV (setCsvData) e na tabela (setDataTableData).

```jsx
        const controller = new AbortController();
        const handleFetch = async () => {
            setLoading(true);
            try {
                const data = await fetchSyntheticReport(classId, studyId, controller);
                setStudyTitle(data.study.description);
                setClassTitle(`${data.sclass.description} (${data.sclass.semester}/${data.sclass.year})`);

                const newChartData = [["Element", "Quantide de alunos por habilidade", { role: "style" }]];
                data.study.options.map((option, index) => newChartData.push([option.description, option.count, colors[index]]));
                setChartData(newChartData);

                const newRows = data.study.options.map((option, index) => 
                    createData(
                        index,
                        option.description,
                        option.value
                    )
                );
                
                let newCsvData = [];
                newRows.map((row) => (
                    newCsvData.push(
                        {
                            habilidade: row.description,
                            media: row.value.toFixed(4),
                        }
                    )
                ));
                setCsvData(newCsvData);
                
                setDataTableData(newRows);
            } catch (error) {
                if (error.name !== 'AbortError') {
                    console.log("Error during fetch:", error);
                }
            } finally {
                setLoading(false);
            }
        }

        handleFetch();

        return () => controller.abort();
```