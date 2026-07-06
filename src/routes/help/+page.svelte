<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Help Desk | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad Help Desk — file tickets for any campus issue from broken doors to account resets." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-help">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Help Desk</h1>
		<p class="subtitle">help.iiit.ac.in</p>

		<h2>What is it?</h2>
		<p>
			<a href="https://help.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				help.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the official help desk where you can file a ticket for <strong>literally
			anything</strong> — from a broken door handle to an account reset request.
		</p>
		<p>
			Just log in with your <strong>LDAP credentials</strong>, select the relevant section,
			fill in the details, and you're done. Someone will get back to you.
		</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #ecfdf5; border-color: #34d399;">
			<p>
				<strong>Tip.</strong> This portal will solve most of your daily issues — use it
				as much as you can. It's the fastest way to get things done.
			</p>
		</div>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://help.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Help Desk
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>