<script lang="ts">
	import Foto from "./assets/minha_foto.jpg"
	import IconeEMail from "./lib/IconeEMail.svelte";
	import IconeGH from "./lib/IconeGH.svelte"
	import CMDLine from "./lib/CMDLine.svelte";

</script>

<main>
	<div class="sobre-mim">
		
		<img src={Foto} alt="foto minha" style="grid-area: fot">

		<div class="infos">
			<div class="vulgo">
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
			</div>
			<h1 style="grid-area: sau">
				<CMDLine 
					cursor={false}
					tokens={[
					["echo", "palavra-chave"],
					[" ", "espaco"],
					["\\", "operador"],
				]}/>
				<br>
				<CMDLine 
					cursor={true}
					cifrao={false}
					tokens={[
					['"oi, eu sou o', "primitivo"],
					[" ", "espaco"],
					["$BRENO", "variavel"],
					['"', "primitivo"],
				]}/>
			</h1>
			<h2 >
				<CMDLine 
					tokens={[
					["cat", "palavra-chave"],
					[" ", "espaco"],
					['sobre-mim.md', "primitivo"],
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
			['socials', "primitivo"],
		]}/>
	</div>
	<div class="sociais">
		<a href="https://github.com/BreakNoh" class="link-social"><IconeGH/>github</a>
		<a href="mailto://eu@bre.dev.br"class="link-social"><IconeEMail/>contato</a>
	</div>
</footer>


<style>
	main {
		padding-block: 2rem;
		padding-inline: 3rem;
		background-color: var(--fundo-1);
		border-radius: 16px;

		margin-top: max(5%, 1rem);

		margin-inline: clamp(1rem, 15%, 30rem);
		@media screen and (width <= 950px){
			margin-inline: clamp(.5rem, 5%, 5rem);
		}
	}
	p {
		color: white;
		max-width: 30rem;
	}
	h1 {
		margin-block: .5rem 1rem;
		font-size: clamp(16px, 5vw, 32px);
	}
	h2 {
		margin-block: 1rem .5rem;
		font-size: clamp(8px, 5vw, 24px);
	}
	img {
		aspect-ratio: 3 / 4;
		margin-inline: auto;
		border-radius: 20px;
		height: max(80px, 30vh);
	}
	
	.sobre-mim {
		display: flex;
		align-items: center;
		column-gap: 1rem;

		@media screen and (width <= 850px){
			flex-direction: column;
			row-gap: 1rem;

			& .infos .vulgo {
				text-align: center;
			}
		}
	}

	footer {
		display: grid;
		justify-content: center;
		margin-top: 3rem;
	}
	footer div {
		text-align: center;
	}

	.sociais {
		margin-top: .5rem;
		display:  flex;
		column-gap: 2rem;
	}
	.sociais a {
		display: grid;
		column-gap: .5rem;
		text-decoration: none;
		grid-template-columns: 1.5rem 1fr;
		color: white;
	}
	.sociais a:hover {
		text-decoration: underline;
	}
</style>
