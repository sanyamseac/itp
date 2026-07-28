<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Almanac | IIIT Hyderabad Intro to Portals Guide</title>
	<meta
		name="description"
		content="IIIT Hyderabad Almanac — academic calendar with semester dates, deadlines, and breaks."
	/>
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-almanac">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Almanac</h1>
		<p class="subtitle">almanac.iiit.ac.in</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> The almanac is accessible from IIIT WiFi or LAN. Off
				campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<h2>What is it?</h2>
		<p>
			<a
				href="https://almanac.iiit.ac.in"
				target="_blank"
				rel="noopener noreferrer"
				class="inline-link"
			>
				almanac.iiit.ac.in <ArrowUpRight size={14} /></a
			>
			is the institute's academic calendar with important semester dates, deadlines, holidays, and breaks.
		</p>

		<div style="margin-top: 2rem;">
			<button
				class="cta-btn"
				onclick={() => window.open('https://almanac.iiit.ac.in', '_blank', 'noopener,noreferrer')}
			>
				Open Almanac
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>
