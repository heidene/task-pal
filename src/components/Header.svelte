<script>
	import { appWindow } from '@tauri-apps/api/window';

	function minimize() {
		appWindow.minimize();
	}

	function maximize() {
		appWindow.maximize();
	}

	function close() {
		appWindow.close();
	}
</script>

<header data-tauri-drag-region class="p-4 relative sticky top-0 bg-surface-900">
	<div class="flex justify-start content-center gap-2 absolute top-4 left-4">
		<button class="rounded-full p-0 w-4 h-4 bg-error-500" id="titlebar-close" on:click={close} />
		<button
			class="rounded-full p-0 w-4 h-4 bg-warning-500"
			id="titlebar-minimize"
			on:click={minimize}
		/>
		<button
			class="rounded-full p-0 w-4 h-4 bg-success-500"
			id="titlebar-maximize"
			on:click={maximize}
		/>
	</div>
	<h1
		class="pointer-events-none bg-gradient-to-br from-blue-500 to-cyan-300 bg-clip-text text-transparent box-decoration-clone text-center h-4 font-heading-token text-xs"
	>
		Add Quick Task
	</h1>
</header>
