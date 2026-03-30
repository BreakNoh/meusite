<script lang="ts">
	 import Html5 from "./assets/html5.svg"
	 import Python from "./assets/python.svg"
	 import Rust from "./assets/rust_dark.svg"
	 import Foto from "./assets/minha_foto.jpg"
	 import GitHub from "./assets/github_dark.svg"
	 import EMail from "./assets/mail.svg"


	let tecnoligia_em_destaque:"web" | "python" | "rust" = $state("python")
</script>

<main>

	<div class="sobre-mim">
		
		<img src={Foto} alt="foto minha" height="250" style="grid-area: fot">

		<h1 style="grid-area: sau">Oi, eu sou o <strong>Breno</strong></h1>

		<p style="grid-area: bio">
			Sou um dev entusiasta, e desejo poder trabalhar na área.
			Gosto de conhecer tecnologias novas, e me desafiar a me manter 
			criativo e inovador.
		</p>

	</div>

	<div class="tecnologias">
		<button onclick={()=>tecnoligia_em_destaque="web"}>
			<img src={Html5} alt="logo do html5" class="icone"/>
			web
		</button>
		<button onclick={()=>tecnoligia_em_destaque="python"}>
			<img src={Python} alt = "logo do python"class="icone"/>
			python
		</button>
		<button onclick={()=>tecnoligia_em_destaque="rust"}>
			<img src={Rust} alt="logo do rust"class="icone"/>
			rust
		</button>
	</div>

	<div class="projetos">
		{#if tecnoligia_em_destaque=="web"}
			esse site
		{:else if tecnoligia_em_destaque == "python"}
			obinus
		{:else}
			tet_rs
		{/if}
	</div>

</main>

<footer>
	<a href="https://github.com/BreakNoh"><img src={GitHub} alt="logo do github" class="icone"/>github</a>
	<a href="mailto://eu@bre.dev.br"><img src={EMail} alt="icone de carta" class="icone"/>contato</a>
</footer>


<style>
	main {
		margin-inline: min(15%, 30rem);

		@media screen and (width <= 500px){
			margin-inline: 1rem;
		}
	}
	.tecnologias {
		display: flex;

		& button {
			flex: 1
		}
	}
	img {
		margin-inline: auto;
	}
	.sobre-mim {
		display: grid;
		
		grid-template-areas: "fot sau" "fot bio";

		@media screen and (width <= 600px){
			grid-template-areas: "fot" "sau" "bio";
		}
	}
	.icone{
		aspect-ratio: 1 / 1;
		height: 2rem;
	}
</style>
