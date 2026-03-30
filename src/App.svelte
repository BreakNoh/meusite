<script lang="ts">
	 import Html5 from "./assets/html5.svg"
	 import Python from "./assets/python.svg"
	 import Rust from "./assets/rust_dark.svg"
	 import Foto from "./assets/minha_foto.jpg"
	 import GitHub from "./assets/github_dark.svg"
	 import EMail from "./assets/mail.svg"


	let tecnoligia_em_destaque:"web" | "python" | "rust" = $state("python")
</script>

<!-- <canvas class="fundo"></canvas> -->

<main>

	<div class="sobre-mim">
		
		<img src={Foto} alt="foto minha" height="300">

		<h1>Oi, eu sou o <strong>Breno</strong></h1>

		<p>
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
	<img src={GitHub} alt="logo do github" class="icone"/>
	<a href="https://github.com/BreakNoh">github</a>
	<img src={EMail} alt="icone de carta" class="icone"/>
	<a href="mailto://eu@bre.dev.br">contato</a>

</footer>


<style>
	.icone{
		aspect-ratio: 1 / 1;
		height: 2rem;
	}
</style>
