<script lang="ts">
	import { Modal } from '@skeletonlabs/skeleton-svelte';

	let openState = $state(false);

	function modalClose() {
		openState = false;
	}
</script>

<Modal
	triggerBase="btn preset-tonal"
	contentBase="card bg-surface-100-900 p-4 space-y-4 shadow-xl max-w-screen-sm"
	backdropClasses="backdrop-blur-sm"
>
	{#snippet trigger()}Open Modal (Working){/snippet}
	{#snippet content()}
		<header class="flex justify-between">
			<h2 class="h2">Working Modal</h2>
		</header>
		<article>
			<p class="opacity-60">
				When closing this modal via clicking outside or <kbd class="kbd">esc</kbd>, an animation
				will play. Everything works as expected!
			</p>
		</article>
		<footer class="flex justify-end gap-4">
			<button type="button" class="btn preset-tonal" disabled onclick={modalClose}>Cancel</button>
			<button type="button" class="btn preset-filled" disabled onclick={modalClose}>Confirm</button>
		</footer>
	{/snippet}
</Modal>

<Modal
	open={openState}
	onOpenChange={(e) => (openState = e.open)}
	triggerBase="btn preset-tonal"
	contentBase="card bg-surface-100-900 p-4 space-y-4 shadow-xl max-w-screen-sm"
	backdropClasses="backdrop-blur-sm"
>
	{#snippet trigger()}Open Modal (Broken){/snippet}
	{#snippet content()}
		<header class="flex justify-between">
			<h2 class="h2">Broken Modal</h2>
		</header>
		<article>
			<p class="opacity-60">
				When closing this modal, no animation will play. A closing animation is expected, so
				something is wrong!
			</p>
		</article>
		<footer class="flex justify-end gap-4">
			<button type="button" class="btn preset-tonal" onclick={modalClose}>Cancel</button>
			<button type="button" class="btn preset-filled" onclick={modalClose}>Confirm</button>
		</footer>
	{/snippet}
</Modal>
