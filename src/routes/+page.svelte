<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowUpRight } from '@lucide/svelte';

	// ── Card data ──
	const cardData = [
		{
			slug: 'welcome',
			title: 'Welcome to IIIT',
			redirectUrl: 'https://www.iiit.ac.in',
			gradient: 'from-amber-50 via-orange-50/50 to-rose-50',
			viewName: 'card-welcome'
		},
		{
			slug: 'ldap',
			title: 'What is LDAP?',
			redirectUrl: null,
			gradient: 'from-sky-50 via-blue-50/50 to-indigo-50',
			viewName: 'card-ldap'
		},
		{
			slug: 'passwordreset',
			title: 'Reset Your Password',
			redirectUrl: 'https://passwordreset.iiit.ac.in',
			gradient: 'from-violet-50 via-purple-50/50 to-fuchsia-50',
			viewName: 'card-passwordreset'
		},
		{
			slug: 'wifi',
			title: 'Connect to WiFi',
			redirectUrl: null,
			gradient: 'from-emerald-50 via-teal-50/50 to-cyan-50',
			viewName: 'card-wifi'
		},
		{
			slug: 'ethernet',
			title: 'Wired Ethernet',
			redirectUrl: null,
			gradient: 'from-stone-50 via-neutral-50/50 to-zinc-50',
			viewName: 'card-ethernet'
		}
	];

	// ── Shared state ──
	let activeIndex = $state(0);

	// ── Container ref ──
	let scrollContainer = $state<HTMLDivElement>();

	// Set up observer when container is available
	$effect(() => {
		const container = scrollContainer;
		if (!container) return;

		// Restore saved card position when coming back from a detail page
		const savedIndex = sessionStorage.getItem('cardIndex');
		if (savedIndex !== null) {
			sessionStorage.removeItem('cardIndex');
			const idx = parseInt(savedIndex, 10);
			requestAnimationFrame(() => {
				const cards = container.querySelectorAll('.mobile-card');
				if (cards[idx]) {
					cards[idx].scrollIntoView({ behavior: 'instant', block: 'nearest', inline: 'start' });
				}
			});
		}

		const observer = new IntersectionObserver(
			(entries) => {
				for (const entry of entries) {
					if (entry.isIntersecting) {
						const idx = Number(entry.target.getAttribute('data-index'));
						if (!isNaN(idx)) activeIndex = idx;
					}
				}
			},
			{ threshold: 0.5 }
		);
		const cards = container.querySelectorAll('.mobile-card');
		cards.forEach((c) => observer.observe(c));
		return () => observer.disconnect();
	});

	// Keyboard left/right navigation
	$effect(() => {
		function handleKey(e: KeyboardEvent) {
			if (e.key !== 'ArrowRight' && e.key !== 'ArrowLeft') return;
			e.preventDefault();
			const container = scrollContainer;
			if (!container) return;
			const cards = container.querySelectorAll('.mobile-card');
			const current = activeIndex;
			let next = current;
			if (e.key === 'ArrowRight' && current < cards.length - 1) next = current + 1;
			if (e.key === 'ArrowLeft' && current > 0) next = current - 1;
			if (next !== current) {
				cards[next].scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'start' });
			}
		}
		window.addEventListener('keydown', handleKey);
		return () => window.removeEventListener('keydown', handleKey);
	});

	function goTo(slug: string, index: number) {
		sessionStorage.setItem('cardIndex', String(index));
		goto(`/${slug}`);
	}

	function openExternal(url: string) {
		window.open(url, '_blank', 'noopener,noreferrer');
	}
</script>

<!-- ────────────── HORIZONTAL SCROLL CARDS (all screens) ────────────── -->
<div
	bind:this={scrollContainer}
	class="mobile-scroll"
>
	{#each cardData as card, i (card.slug)}
		<section
			class="mobile-card bg-gradient-to-br {card.gradient}"
			data-index="{i}"
			style="view-transition-name: {card.viewName}"
			onclick={() => goTo(card.slug, i)}
			onkeydown={(e) => e.key === 'Enter' && goTo(card.slug, i)}
			role="button"
			tabindex="0"
		>
			{#if card.redirectUrl}
				<button
					class="redirect-btn"
					onclick={(e) => {
						e.stopPropagation();
						openExternal(card.redirectUrl!);
					}}
					aria-label="Open external link"
				>
					<ArrowUpRight size={20} />
				</button>
			{/if}

			<div class="card-content">
				<h1 class="card-title">{card.title}</h1>
			</div>
		</section>
	{/each}
</div>

<!-- Tap to explore + page dots -->
<div class="mobile-bottom">
	<p class="tap-hint">tap to explore</p>
	<div class="mobile-dots">
		{#each cardData as _, i}
			<button
				class="mobile-dot {i === activeIndex ? 'active' : ''}"
				onclick={() => {
					const cards = scrollContainer?.querySelectorAll('.mobile-card');
					if (cards?.[i]) {
						cards[i].scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'start' });
					}
				}}
				aria-label="Go to card {i + 1}"
			></button>
		{/each}
	</div>
</div>
