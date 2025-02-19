---
title: "Criar nova senha"
permalink: /dev/novasenha/
excerpt: "Página de Nova senha"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O componente PasswordResetConfirmation apresenta os dois arquivos principais index.jsx e styles.css, como ilustrado na Figura:

![modulos](/assets/images/code6.png)

Caso a solicitação de troca de senha seja bem-sucedida, o usuário receberá um e-mail contendo um link com a URL da página de redefinição de senha e um token de validação. O código ilustra a função responsável por processar a submissão do formulário de redefinir senha. Após submeter o formulário, o usuário é redirecionado automaticamente para a tela de login.

```jsx
    const onSubmit = async (event) => {
        event.preventDefault();

        if (!(validatePassword())) return;

        setLoading(true);
        const { success, message } = await resetPassword(token, passwordReset);
        if (!success) {
            setMessageType("error");
            setMessage(message || "Ocorreu uma falha durante a solicitação de alteração da sua senha.");
            setOpen(true);
        } else {
            setMessageType("success");
            setMessage("Senha alterada com sucesso. Redirecionando para a página de login.")
            setOpen(true);
            setTimeout(() => {
                navigate("/login/");
            }, 3000);
        }
        setLoading(false);
    };
```