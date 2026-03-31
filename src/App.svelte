<script lang="ts">
	 import Foto from "./assets/minha_foto.jpg"
    import IconeEMail from "./lib/IconeEMail.svelte";
	 import IconeGH from "./lib/IconeGH.svelte"


	let tecnoligia_em_destaque:"web" | "python" | "rust" = $state("python")
</script>

<main>
	<div class="sobre-mim">
		
		<img src={Foto} alt="foto minha" height="250" style="grid-area: fot">

		<div style="grid-area: sau" class="saudacao">
			<span class="vulgo">
				<span class="keyword">export</span> 
				{" "}
				<span class="var">BRENO</span>{"="}<span class="string">"BreakNoh"</span>
			</span>
			<h1 style="grid-area: sau">
				<span class="cifrao">$</span> 
				{" "}
				<span class="cmd">echo</span> 
				{" "}
				<span class="string">
					"oi, eu sou o 
					<span class="var">$BRENO</span>"
				</span><span class="cursor">
					_
				</span>
			</h1>
		</div>


		<div style="grid-area: bio">
			<h2 >
				<span class="cifrao">$</span> 
				{" "}
				<span class="cmd">cat</span> 
				{" "}
				<span class="string">
					./descricao.md
				</span><span class="cursor">
					_
				</span>

			</h2>
			<p>
			Sou um dev entusiasta, e desejo poder trabalhar na área.
			Gosto de conhecer tecnologias novas, e me desafiar a me manter 
			criativo e inovador.

			</p>
		</div>

	</div>

</main>

<footer>
	<span>
		<span class="cifrao">$</span> 
		{" "}
		<span class="cmd">ls</span> 
		{" "}
		<span class="string">
			./sociais
		</span><span class="cursor">
			_
		</span>

	</span>

	<div class="sociais">
		<a href="https://github.com/BreakNoh" class="link-social"><IconeGH/> github</a>
		<a href="mailto://eu@bre.dev.br"class="link-social"><IconeEMail/> contato</a>
	</div>
</footer>


<style>
	:global(:root) {
		background-color: var(--fundo-0);
	}
	:global(html, body) {
        margin: 0;  
        padding: 0;
    }
	main {
		padding-block: 2rem;
		padding-inline: 4rem;
		background-color: var(--fundo-1);
		margin-inline: min(10%, 30rem);
		border-radius: 16px;

		margin-top: max(5%, 1rem);

		@media screen and (width <= 500px){
			margin-inline: 1rem;
		}
	}
	p {
		color: white;
		max-width: 30rem;
	}
	.link-social {
		display: grid;
		column-gap: .5rem;
		text-decoration: none;
		grid-template-columns: 1.5rem 1fr;
		color: white;
	}
	.keyword {
		color: var(--sec)
	}
	.string {
		color: var(--ter)
	}
	.var {
		color: var(--prim)
	}
	.cifrao {
		color: white;
	}
	.cmd {
		color: var(--sec);
	}

	@keyframes piscar {
		0% {
			opacity: 1;
		}
		50% {
			opacity: 0;
		}
	}

	.cursor {
		animation-name: piscar;
		animation-duration: 2s;
		animation-delay: 0;
		animation-timing-function: step-end;
		animation-iteration-count: infinite;
	}

	img {
		margin-inline: auto;
		border-radius: 20px;
	}
	footer {
		text-align: center;
		margin-top: 3rem;
	}
	.sociais {
		margin-top: .5rem;
		display:  flex;
		justify-content: center;
		column-gap: 2rem;
	}

	h1 {
		margin-block: .5rem 1rem;
	}
	h2 {
		margin-block: 1rem .5rem;
	}

	.sobre-mim {
		display: grid;
		
		grid-template-areas: "fot sau" "fot bio";
		column-gap: 1rem;
		grid-template-rows: auto 1fr;

		@media screen and (width <= 850px){
			grid-template-areas: "fot" "sau" "bio";
		}
	}
	.icone{
		aspect-ratio: 1 / 1;
		height: 2rem;
	}

</style>
