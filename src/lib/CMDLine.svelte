<script lang="ts">
	type Props = {
		tokens: string[][],
		cifrao?: boolean,
		cursor?: boolean,
	}
	let {tokens = [], cifrao = true, cursor = true} : Props= $props()	
</script>

<span class="cmdline">
	{#if cifrao}
		<span class="cifrao">&dollar;</span>
	{/if}
	{#each tokens as tkn}
		{@const [val, papel] = tkn}	
		<span class={["token", papel]}>{val}</span>
	{/each}
	{#if cursor}
		<span class="cursor">&UnderBar;</span>
	{/if}
</span>


<style>
	.espaco{
		width: 1rem;
	}
	.palavra-chave {
		color: var(--sec)
	}
	.primitivo {
		color: var(--ter)
	}
	.variavel {
		color: var(--prim)
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
		animation-duration: 1.5s;
		animation-delay: 0;
		animation-timing-function: step-end;
		animation-iteration-count: infinite;
	}
</style>
