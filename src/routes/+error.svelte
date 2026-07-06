<script lang="ts">
	import { goto } from '$app/navigation';
	import { page } from '$app/state';
	import { ArrowLeft } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Error {page.status || 'Unknown'} | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="Something went wrong." />
</svelte:head>

<div class="detail-overlay">
	<div class="detail-content" style="text-align: center; padding-top: 4rem;">
		<h1 style="font-size: 4rem; margin: 0; line-height: 1;">{page.status || '?'}</h1>
		<p class="subtitle" style="margin-top: 0.5rem;">
			{page.error?.message || 'An unexpected error occurred.'}
		</p>

		<div class="section-divider"></div>

		<p>Something went wrong while loading this page.</p>

		<button class="cta-btn" onclick={() => goto('/')} style="margin-top: 2rem;">
			<ArrowLeft size={16} /> Back to Home
		</button>
	</div>
</div>
