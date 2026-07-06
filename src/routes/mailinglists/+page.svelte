<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Mailing Lists | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad student mailing lists — how to join UG1, batch-wide announcements, and manage your subscriptions." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-mailinglists">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Mailing Lists</h1>
		<p class="subtitle">Campus mailing groups you'll be part of</p>

		<div class="section-divider"></div>

		<h2>Your Key Lists</h2>
		<p>There are three mailing lists you should know about right away:</p>

		<div class="domain-grid">
			<div class="domain-card">
				<h3>students@lists.iiit.ac.in</h3>
				<p>Your official mailing list — all academic and admin announcements go here. You're automatically subscribed.</p>
			</div>
			<div class="domain-card">
				<h3>life@lists.iiit.ac.in</h3>
				<p>Unofficial list for campus life — club updates, events, casual conversations, and general chatter.</p>
			</div>
		</div>

		<div class="section-divider"></div>

		<h2>Your Batch List</h2>
		<p>
			You'll be subscribed to your branch's mailing list automatically.
			For UG1 students, the lists are organized by branch:
		</p>
		<pre><code>ug1 => ug1_cse, ug1_ece, ug1dual
ug1dual => ug1_csdual, ug1_ecdual,
           ug1_cldual, ug1_cnsdual,
           ug1_cgdual, ug1_chdual</code></pre>

		<div class="section-divider"></div>

		<h2>Manage Your Subscriptions</h2>
		<p>
			Visit
			<a href="https://lists.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				lists.iiit.ac.in <ArrowUpRight size={14} />
			</a>
			and sign in with your <strong>LDAP credentials</strong>. From there, you can
			browse all available lists and manage your subscriptions. Note that the website
            may not allow you to unsubscribe or manage some lists, to which your subscription
            is mandatory.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://lists.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Browse Mailing Lists
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>
