<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-library">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Library</h1>
		<p class="subtitle">library.iiit.ac.in</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> The library portal is accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<h2>What is it?</h2>
		<p>
			<a href="https://library.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				library.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the library portal where you can request books, browse e-books, and access
			online journals.
		</p>

		<div class="section-divider"></div>

		<h2>OPAC</h2>
		<p>
			Click on <strong>OPAC</strong> in the navbar — it opens the catalogue where you
			can search for any book in the library. The search result gives you a
			<strong>shelf number</strong> that tells you exactly which rack and shelf to
			walk to and grab the book.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://library.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Library Portal
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>