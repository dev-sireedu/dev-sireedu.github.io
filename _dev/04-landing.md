---
title: "Landing Page"
permalink: /dev/landing/
excerpt: "Landing Page"
last_modified_at: 2025-01-25T08:48:05-04:00
---

Como ilustrado na Figura abaixo, a Landing Page é organizada em seções distintas, representando partes específicas da interface. Isso ajuda na modularidade e reutilização dos componentes:

1. Home: seção principal que introduz o SIREEDU.
2. About: apresenta os detalhes sobre o projeto.
3. Differences: destaca os diferenciais da aplicação.
4. Intended: explica o público-alvo, fornecendo mais contexto aos usuários.
5. OurOffer: mostra os recursos oferecidos.

![modulos](/assets/images/code3.png)

O código ilustra a função LandingPage, responsável por retornar os elementos JSX que representam a página. É possível observar que as seções são estruturadas utilizando a tag <section>, proporcionando melhor acessibilidade e SEO.

```jsx
const LandingPage = () => {
	const { authenticated } = useContext(Context);

	if (authenticated) {
		return <Navigate to="/home" />
	}

	return (
		<div className="landing-page">
			<PageTitleUpdater title={"SIREEDU"} />
			<div className="container">
				<section id="home">
					<Home/>
				</section>
				<section id="about">
					<About />
				</section>
				<section id="differences">
					<Differences />
				</section>
				<section id="intended">
					<Intended />
				</section>
				<section id="our-offer">
					<OurOffer />
				</section>
			</div>
	  	</div>
	);	
}
  
export default LandingPage;
```