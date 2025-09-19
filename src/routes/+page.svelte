<script lang="ts">
	import { Dialog } from '@skeletonlabs/skeleton-svelte';
</script>

<Dialog>
	<Dialog.Trigger class="btn preset-filled">Trigger</Dialog.Trigger>
	<!-- Animating fade in/out -->
	<Dialog.Backdrop
		class="fixed inset-0 z-50 bg-surface-50-950/50 data-[state=open]:animate-[fade-in_100ms_ease-in-out]"
	/>
	<Dialog.Positioner class="fixed inset-0 z-50 flex items-center justify-center">
		<!-- Animating fly in/out -->
		<Dialog.Content
			class="w-md space-y-2 card bg-surface-100-900 p-4 shadow-xl data-[state=open]:animate-[slide-out_100ms_ease-in-out]"
		>
			<Dialog.Title class="text-2xl font-bold">Hello World</Dialog.Title>
			<Dialog.Description>This is an example of a basic dialog.</Dialog.Description>
			<Dialog.CloseTrigger class="btn preset-tonal">Close</Dialog.CloseTrigger>
		</Dialog.Content>
	</Dialog.Positioner>
</Dialog>
