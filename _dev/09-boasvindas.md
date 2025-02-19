---
title: "Boas-vindas"
permalink: /dev/boasvindas/
excerpt: "Página de Boas-vindas"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O diretório Welcome contém componentes individuais Success e Error, responsáveis por renderizar a tela apropriada.

![modulos](/assets/images/code7.png)

Após o envio bem-sucedido do cadastro, o usuário recebe um e-mail com um link de confirmação contendo um token. Ao acessar o link, o sistema realiza a autenticação do token. Se a validação do token for bem-sucedida (isVerify === true), o componente Success é renderizado, exibindo a mensagem de boas-vindas. Caso contrário, o componente Error é exibido, informando ao usuário que houve um erro durante a verificação.

```jsx
        <div className="welcome">
            <SimpleBackdrop open={loading} />
            <div className="welcome-container">
                <PageTitleUpdater title={"Bem-vindo"} />
                {isVerify ? (
                    <Success />
                ) : (
                    <Error />
                )}
            </div>
        </div>
```