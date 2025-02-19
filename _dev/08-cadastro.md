---
title: "Cadastro de aluno"
permalink: /dev/cadastro/
excerpt: "Página de Cadastro de aluno"
last_modified_at: 2025-01-25T08:48:05-04:00
---

O componente SignUp, responsável pelo cadastro de alunos, segue a mesma organização modular das outras páginas da aplicação. A função SignUp implementa um formulário de cadastro dividido em três etapas principais, conforme o trecho de código ilustrado no código:

```jsx
        <div className="signup-container">
            <PageTitleUpdater title={"Registrar-se"}/>
            <SimpleBackdrop open={loading} />
            {!showEmailVerification &&
            <div>
                <div className="signup-content">
                    <div className="marker-container">
                        {marker.map((item) => (
                            <Marker
                                key={item.section} 
                                section={item.section} 
                                status={item.status} 
                            />
                        ))}
                    </div>
                    <form className="signup-form" onSubmit={onSubmit} id="signupForm">
                        {/* name and last name */}
                        <div className={`step ${marker[0].activeStep ? "active" : "hidden"}`}>

                            <div>
                                <p className="signup-heading">Registre-se</p>
                            </div>

                            <NameSection
                                name={formData.name}
                                nameError={fieldError.name}
                                lastName={formData.lastName}
                                lastNameError={fieldError.lastName}
                                handleFieldChange={handleFieldChange}
                                handleNext={handleNext}
                            />
                        </div>
                        
                        {/* email and password */}
                        <div className={`step ${marker[1].activeStep ? "active" : "hidden"}`}>
                            <EmailAndPasswordSection 
                                email={formData.email}
                                emailError={fieldError.email}
                                passwordError={fieldError.password}
                                passwordConfirmationError={fieldError.passwordConfirmation}
                                handleFieldChange={handleFieldChange}
                                handleNext={handleNext}
                            />
                        </div>

                        {/* institution and course */}
                        <div className={`step ${marker[2].activeStep ? "active" : "hidden"}`}>
                            <InstitutionSection
                                institution={formData.institution}
                                institutionError={fieldError.institution}
                                institutions={institutions}
                                selectedInstitutionChanged={selectedInstitutionChanged}
                                program={formData.program}
                                programError={fieldError.program}
                                programs={programs}
                                selectedProgramChanged={selectedProgramChanged}
                                programClass={formData.programClass}
                                programClassError={fieldError.programClass}
                                handleFieldChange={handleFieldChange}
                                programClasses={programClasses}
                            />
                        </div>

                        {open && <MessageHandler message={message} type={messageType} open={open} onClose={handleClose} />}

                        <div className="step-buttons-container">
                            {
                            <div className="step-buttons">
                            {marker[2].activeStep &&
                                <button type="submit"> 
                                    Enviar
                                </button>
                            }

                            {!marker[2].activeStep &&
                                <button type="button" onClick={handleNext}>
                                    Próximo
                                </button>
                            }

                            {!marker[0].activeStep &&
                                <button type="button" onClick={handleBack}>
                                    Voltar
                                </button>
                            }
                            </div>
                            }
                        </div>
                    </form>
                </div>
                <div style={{ margin: "1rem 0" }}>
                    <p className="create-account-text">
                        Já possui uma conta? <Link className="primary-color create-account-link" to="/login/">Faça login</Link>
                    </p>
                </div>
            </div>
            }

            {showEmailVerification &&
                <EmailVerification email={formData.email}/>
            }
            
        </div>
```