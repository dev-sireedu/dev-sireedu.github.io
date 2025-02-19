---
title: "Esqueceu a senha"
permalink: /dev/esqueceu/
excerpt: "Página de Esqueceu a senha"
last_modified_at: 2025-01-25T08:48:05-04:00
---

Novamente temos padrão adotado no projeto, com os dois arquivos principais index.jsx e styles.css, como ilustrado na Figura:

![modulos](/assets/images/code5.png)

O código a seguir apresenta o trecho central da função PasswordReset. Ao preencher o campo de e-mail e submeter o formulário, o usuário é redirecionado para uma tela de confirmação de envio de e-mail.

```jsx
        <div className="password-reset-container">
            <PageTitleUpdater title={"Redefinir senha"} />
            <div className="password-reset-content">
                {!showMessage &&
                <div>
                    <p className="password-reset-title">Redefinir senha</p>
                    <form onSubmit={onSubmit}>
                        <p className="password-reset-text">Preencha o campo abaixo para solicitar a recuperação de senha.</p>
                        {emailError && <span className="error-message">Utilize um e-mail institucional</span>}
                        <FormControl fullWidth sx={{ width: '100%', marginBottom: '15px' }}>
                            <OutlinedInput
                                id="email"
                                placeholder="E-mail de acesso"
                                onChange={(e) => setEmail(e.target.value)}
                                error={emailError}
                                required
                            />
                        </FormControl>
                        {open && <MessageHandler message={error} type={messageType} open={open} onClose={handleClose} />}
                        <button className="password-reset-button bg-primary-color" type="submit">
                            {loading ? <CircularProgress size={24} color="inherit" /> : "Enviar"}
                        </button>
                        <p className="instruction-message">
                            Você irá receber um e-mail no endereço informado acima contendo o procedimento
                            para criar uma nova senha para esse usuário.
                        </p>
                        <div style={{'margin-top': '10px'}}>
                            <Link className="login-link" to="../login">Voltar para tela de login</Link>
                        </div>
                    </form>
                </div>
                }
                {showMessage &&
                <div>
                    <p className="password-reset-title">E-mail enviado!</p>
                    <p className="instruction-message">
                        Um e-mail foi enviado para <span className="email">{email}</span> com as instruções e um link para alteração da senha. 
                        Caso você não receba o e-mail em alguns minutos, verifique a sua caixa de spam ou repita o processo.
                    </p>
                    <div className="reset-image-section">
                        <img src={SendInvite} alt="SendInvite"/>
                    </div>
                    <div>
                        <Link className="login-link" to="../login">Voltar para tela de login</Link>
                    </div>
                </div>
                }
            </div>
        </div>
```