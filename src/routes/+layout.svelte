<script lang="ts">
	import './layout.css';
	import { onNavigate } from '$app/navigation';
	import { browser } from '$app/environment';

	const { children } = $props();

	if (browser) {
		onNavigate((navigation) => {
			if (!document.startViewTransition) return;
			return new Promise((resolve) => {
				document.startViewTransition(async () => {
					resolve();
					await navigation.complete;
				});
			});
		});
	}
</script>

{@render children()}
