<script>
	import { onMount } from 'svelte';
	const { children, onFechar } = $props();

	function handleKeydown(event) {
		// Fecha o modal se o usuário pressionar a tecla "Escape"
		if (event.key === 'Escape') {
			onFechar();
		}
	}
</script>

<svelte:window onkeydown={handleKeydown} />

<div class="backdrop">
	<div class="modal-content" role="dialog" aria-modal="true">
		<button class="botao-fechar" onclick={onFechar}>&times;</button>
		{@render children()}
	</div>
</div>

<style>
	.backdrop {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.6);
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 100;
	}

	.modal-content {
		background-color: white;
		padding: 2rem;
		border-radius: 8px;
		box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
		position: relative;
		min-width: 300px;
		max-width: 90vw;
	}

	.botao-fechar {
		position: absolute;
		top: 10px;
		right: 15px;
		background: none;
		border: none;
		font-size: 1.5rem;
		cursor: pointer;
		color: #333;
	}
</style>