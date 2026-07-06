<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Self-Help | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad Self-Help wiki — community-maintained information about campus life, academics, and tips." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-selfhelp">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Self-Help</h1>
		<p class="subtitle">self-help.iiit.ac.in</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #fef9c3; border-color: #facc15;">
			<p>
				<strong>Only works on campus.</strong> Self-help is accessible from IIIT WiFi
				or LAN. Off campus?
				<a href="/vpn" class="inline-link">Connect via VPN <ArrowUpRight size={14} /></a> first.
			</p>
		</div>

		<h2>What is it?</h2>
		<p>
			<a href="https://self-help.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				self-help.iiit.ac.in <ArrowUpRight size={14} /></a>
			is a community-maintained wiki with a ton of useful information about IIIT —
			from academic tips to campus life hacks. Just keep in mind that some of it
			may be outdated.
		</p>

		<div class="section-divider"></div>

		<h2>Editing</h2>
		<p>
			Anyone can contribute! To make changes, go to
			<strong>Menu Bar → Quick Links → Login</strong>, and start editing.
			The more people update it, the more accurate it stays.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://self-help.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Self-Help
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>