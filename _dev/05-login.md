---
title: "Login"
permalink: /dev/login/
excerpt: "Página de Login"
last_modified_at: 2025-01-25T08:48:05-04:00
---

A página de Login segue o padrão adotado no projeto, com os dois arquivos principais index.jsx e styles.css, conforme ilustrado na Figura:

![modulos](/assets/images/code4.png)

O código abaixo apresenta um trecho do formulário de login, contendo os campos de e-mail e senha. Nela, destaca-se a obrigatoriedade do uso de um e-mail institucional como requisito para acessar o sistema.

```jsx
		<div className="login-container">
            <PageTitleUpdater title={"Login"} />
            <form className="form-container" onSubmit={onSubmit}>
                <p className="login-heading">Faça seu login</p>
                {emailError && <span className="error-message">Utilize um e-mail institucional</span>}
                <FormControl fullWidth sx={{ width: '100%', marginBottom: '10px' }}>
                    <OutlinedInput
                        id="email"
                        placeholder="Email"
                        startAdornment={<InputAdornment position="start"><MailOutlineIcon /></InputAdornment>}
                        onChange={(e) => setUsername(e.target.value)}
                        required
                        error={emailError}
                    />
                </FormControl>

                <FormControl sx={{ width: '100%', marginBottom: '10px' }}>
                    <OutlinedInput
                        id="outlined-adornment-password"
                        placeholder="Senha"
                        type={showPassword ? 'text' : 'password'}
                        onChange={(e) => setPassword(e.target.value)}
                        required
                        startAdornment={<InputAdornment position="start"><LockIcon /></InputAdornment>}
                        endAdornment={
                        <InputAdornment position="end">
                            <IconButton
                                aria-label="toggle password visibility"
                                onClick={handleClickShowPassword}
                                onMouseDown={handleMouseDownPassword}
                                edge="end"
                            >
                            {showPassword ? <VisibilityOff /> : <Visibility />}
                            </IconButton>
                        </InputAdornment>
                        }
                    />
                </FormControl>

                {open && <MessageHandler message={error} type={messageType} open={open} onClose={handleClose} />}
                
                <div className="forgot-password">
                    <Link className="forgot-password-link" to="../password-reset">Esqueceu a senha?</Link>
                </div>
                
                <button className="bg-primary-color login-button" type="submit" disabled={loading}>
                    {loading ? <CircularProgress size={24} color="inherit" /> : "Entrar"}
                </button>

                <p className="create-account-text">
                    Não tem uma conta? <Link className="primary-color create-account-link" to="/signup/">Crie agora</Link>
                </p>
            </form>

            {openRoleDialog && (
                <Role 
                    open={openRoleDialog} 
                    onClose={handleRoleSelection} 
                    availableRoles={availableRoles} 
                />
            )}
            
        </div>
```