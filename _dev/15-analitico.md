---
title: "Relatório Analítico"
permalink: /dev/analitico/
excerpt: "Página de Relatório Analítico"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O diretório Analytical possui o componente individual DataTable, responsável por renderizar cada tabela de estudo ou inteligência.

![modulos](/assets/images/code14.png)

O trecho de código ilustrado mostra a etapa em que os dados exibidos na página de relatório analitico são tratados para serem usados nas tabelas (setDataTableData) e na exportação em CSV (setCsvData).

```jsx
        const controller = new AbortController();
        const handleFetch = async () => {
            setLoading(true);
            try {
                const data = await fetchAnalyticalReport(classId, studyId, controller);
                setStudyTitle(data.study.description);
                setClassTitle(`${data.sclass.description} (${data.sclass.semester}/${data.sclass.year})`);
                const newData = data.study.options.map((option, index) => 
                    { return { 
                        students: option.students.map((student) => student.first_name + " " + student.last_name),
                        description: option.description,
                        headerColor: colors[index] }
                    }
                );
                setDataTableData(newData);

                const newCsvData = [];
                newData.map((data) => (
                   newCsvData.push(
                        {
                            habilidade: data.description,
                            alunos: data.students.join(",")
                        }
                   ) 
                ));
                setCsvData(newCsvData);

            } catch (error) {
                if (error.name !== 'AbortError') {
                    console.error("Error during fetch:", error);
                }
            } finally {
                setLoading(false);
            }
        }

        handleFetch();

        return () => controller.abort();
```