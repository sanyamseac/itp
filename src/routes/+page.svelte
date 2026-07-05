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
		},
		{
			slug: 'vpn',
			title: 'VPN Access',
			redirectUrl: 'https://vpn.iiit.ac.in',
			gradient: 'from-rose-50 via-pink-50/50 to-fuchsia-50',
			viewName: 'card-vpn'
		},
		{
			slug: 'login',
			title: 'Central Login',
			redirectUrl: 'https://login.iiit.ac.in',
			gradient: 'from-yellow-50 via-amber-50/50 to-orange-50',
			viewName: 'card-login'
		},
		{
			slug: 'outlook',
			title: 'Outlook and M365',
			redirectUrl: 'https://webmail.iiit.ac.in',
			gradient: 'from-indigo-50 via-blue-50/50 to-cyan-50',
			viewName: 'card-outlook'
		},
		{
			slug: 'mailinglists',
			title: 'Mailing Lists',
			redirectUrl: 'https://lists.iiit.ac.in',
			gradient: 'from-teal-50 via-emerald-50/50 to-green-50',
			viewName: 'card-mailinglists'
		},
		{
			slug: 'ims',
			title: 'IMS Portal',
			redirectUrl: 'https://ims.iiit.ac.in',
			gradient: 'from-slate-50 via-gray-50/50 to-zinc-50',
			viewName: 'card-ims'
		},
		{
			slug: 'moodle',
			title: 'Moodle',
			redirectUrl: 'https://courses.iiit.ac.in',
			gradient: 'from-purple-50 via-fuchsia-50/50 to-pink-50',
			viewName: 'card-moodle'
		},
		{
			slug: 'intranet',
			title: 'Intranet',
			redirectUrl: 'https://intranet.iiit.ac.in',
			gradient: 'from-lime-50 via-green-50/50 to-emerald-50',
			viewName: 'card-intranet'
		},
		{
			slug: 'mess',
			title: 'Mess',
			redirectUrl: 'https://mess.iiit.ac.in',
			gradient: 'from-orange-50 via-amber-50/50 to-yellow-50',
			viewName: 'card-mess'
		},
		{
			slug: 'app',
			title: 'My IIIT App',
			redirectUrl: 'https://play.google.com/store/apps/details?id=com.iiith.ims_app',
			gradient: 'from-cyan-50 via-sky-50/50 to-blue-50',
			viewName: 'card-app'
		},
		{
			slug: 'help',
			title: 'Help Desk',
			redirectUrl: 'https://help.iiit.ac.in',
			gradient: 'from-rose-50 via-red-50/50 to-orange-50',
			viewName: 'card-help'
		},
		{
			slug: 'library',
			title: 'Library',
			redirectUrl: 'https://library.iiit.ac.in',
			gradient: 'from-blue-50 via-indigo-50/50 to-violet-50',
			viewName: 'card-library'
		},
		{
			slug: 'selfhelp',
			title: 'Self-Help',
			redirectUrl: 'https://self-help.iiit.ac.in',
			gradient: 'from-pink-50 via-fuchsia-50/50 to-violet-50',
			viewName: 'card-selfhelp'
		},
		{
			slug: 'clubs',
			title: 'Clubs',
			redirectUrl: 'https://clubs.iiit.ac.in',
			gradient: 'from-red-50 via-orange-50/50 to-amber-50',
			viewName: 'card-clubs'
		},
		{
			slug: 'couriers',
			title: 'Couriers',
			redirectUrl: 'https://couriers.iiit.ac.in',
			gradient: 'from-lime-50 via-yellow-50/50 to-amber-50',
			viewName: 'card-couriers'
		},
		{
			slug: 'portals',
			title: 'Portals',
			redirectUrl: 'https://portals.iiit.ac.in',
			gradient: 'from-violet-50 via-blue-50/50 to-sky-50',
			viewName: 'card-portals'
		},
		{
			slug: 'about',
			title: 'About',
			redirectUrl: '',
			gradient: 'from-gray-50 via-neutral-50/50 to-stone-50',
			viewName: 'card-about'
		}
	];

	// ── Shared state ──
	let activeIndex = $state(0);
	let menuOpen = $state(false);

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
			<div class="card-content">
				<h1 class="card-title">{card.title}</h1>
			</div>
		</section>
	{/each}
</div>

<!-- Bottom bar + page dots -->
<div class="mobile-bottom">
	<div class="mobile-bottom-bar">
		{#if cardData[activeIndex]?.redirectUrl}
			<button
				class="redirect-bottom-btn"
				onclick={() => openExternal(cardData[activeIndex].redirectUrl!)}
				aria-label="Open external link"
			>
				<ArrowUpRight size={18} />
			</button>
		{/if}
		<p class="tap-hint">tap to explore</p>
		<button class="menu-btn" onclick={() => menuOpen = true} aria-label="Open menu">
			<span></span><span></span><span></span>
		</button>
	</div>
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

<!-- Menu overlay -->
{#if menuOpen}
	<div class="menu-overlay" onclick={() => menuOpen = false}>
		<div class="menu-content" onclick={(e) => e.stopPropagation()}>
			<div class="menu-header">
				<h2>All Topics</h2>
				<button class="menu-close" onclick={() => menuOpen = false}>✕</button>
			</div>
			{#each cardData as card, i}
				<button class="menu-item" onclick={() => goTo(card.slug, i)}>
					{card.title}
				</button>
			{/each}
		</div>
	</div>
{/if}
