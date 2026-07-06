<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Portals | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad Portals index — master directory of all campus services, including hidden internal tools." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-portals">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Portals</h1>
		<p class="subtitle">portals.iiit.ac.in</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> The portals index is accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<h2>What is it?</h2>
		<p>
			<a href="https://portals.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				portals.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the master index of all official IIIT portals — a directory of pretty much
			every campus service in one place.
		</p>
		<p>
			<strong>But there's more.</strong> A lot of internal tools and services aren't
			listed here — they're only shared via word of mouth, emails, or hidden in
			subdirectories. If you hear about a portal that's not on the list, it probably
			lives somewhere deeper in the intranet.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://portals.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Portals Index
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>