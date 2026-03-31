<script lang="ts">
import Foto from "./assets/minha_foto.jpg"
import IconeEMail from "./lib/IconeEMail.svelte";
import IconeGH from "./lib/IconeGH.svelte"
import CMDLine from "./lib/CMDLine.svelte";


let tecnoligia_em_destaque:"web" | "python" | "rust" = $state("python")
</script>

<main>
	<div class="sobre-mim">
		
		<img src={Foto} alt="foto minha" height="250" style="grid-area: fot">

		<div style="grid-area: sau" class="saudacao">
			<span class="vulgo">
				<CMDLine 
					cursor={false}
					cifrao={false}
					tokens={[
					["export ", "palavra-chave"],
					[" ", "espaco"],
					["BRENO", "variavel"],
					["=", "operador"],
					['"BreakNoh"', "primitivo"],
				]}/>

			</span>
			<h1 style="grid-area: sau">
				<CMDLine 
					tokens={[
					["echo", "palavra-chave"],
					[" ", "espaco"],
					['"oi, eu sou o', "primitivo"],
					[" ", "espaco"],
					["$BRENO", "variavel"],
					['"', "primitivo"],
				]}/>
			</h1>
		</div>


		<div style="grid-area: bio">
			<h2 >
				<CMDLine 
					tokens={[
					["cat", "palavra-chave"],
					[" ", "espaco"],
					['./descricao.md', "primitivo"],
				]}/>
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
	<div>
		<CMDLine 
			tokens={[
			["ls", "palavra-chave"],
			[" ", "espaco"],
			['./socials', "primitivo"],
		]}/>
	</div>
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
		padding-inline: 3rem;
		background-color: var(--fundo-1);
		margin-inline: min(15%, 30rem);
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
	footer {
		display: grid;
		justify-content: center;
		margin-top: 3rem;

		& div {
			text-align: center;
		}
	}
	.link-social {
		display: grid;
		column-gap: .5rem;
		text-decoration: none;
		grid-template-columns: 1.5rem 1fr;
		color: white;

		&:hover {
			text-decoration: underline;
		}
	}

	img {
		margin-inline: auto;
		border-radius: 20px;
	}
	.sociais {
		margin-top: .5rem;
		display:  flex;
		/* justify-content: center; */
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
