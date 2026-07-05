<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<div class="detail-overlay" style="view-transition-name: card-intranet">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Intranet</h1>
		<p class="subtitle">The docs repository</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> The intranet is only accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<h2>What is the Intranet?</h2>
		<p>
			<a href="https://intranet.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				intranet.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the central repository for all official IIIT documents and resources.
			It's highly advised to go through as many documents here as you can —
			everything from academic rules to campus policies lives here.
		</p>

		<div class="section-divider"></div>

		<h2>Bottom Bar</h2>
		<p>
			The bottom bar on the intranet has quick links to the most commonly needed stuff:
		</p>
		<ul class="step-list">
			<li class="step-item"><strong>Timetable</strong> — your class schedule</li>
			<li class="step-item"><strong>Almanac</strong> — academic calendar with all important dates</li>
			<li class="step-item"><strong>Other useful docs</strong> — forms, guidelines, and more</li>
		</ul>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://intranet.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Intranet
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>