<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft, ArrowUpRight } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Clubs | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="IIIT Hyderabad Clubs portal — browse clubs, teams, events, and manage your profile with CAS login." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-clubs">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Clubs</h1>
		<p class="subtitle">clubs.iiit.ac.in</p>

		<div class="section-divider"></div>

		<div class="info-box" style="background: #ecfdf5; border-color: #34d399;">
			<p>
				<strong>Note.</strong> clubs.iiit.ac.in will soon be replaced by
				<strong>life.iiit.ac.in</strong> — the new unified events and clubs platform.
			</p>
		</div>

		<h2>What is it?</h2>
		<p>
			<a href="https://clubs.iiit.ac.in" target="_blank" rel="noopener noreferrer" class="inline-link">
				clubs.iiit.ac.in <ArrowUpRight size={14} /></a>
			is the central portal for everything club-related — browse clubs, see their
			teams and activities, and stay updated on all events happening on campus.
		</p>

		<div class="section-divider"></div>

		<h2>Events</h2>
		<p>
			This is where all events are managed. Once you become a <strong>coordinator</strong>,
			you can apply for new events directly through the portal.
		</p>

		<div class="section-divider"></div>

		<h2>Your Profile</h2>
		<p>
			Sign in with <strong>CAS</strong> and set up your profile — add a profile picture
			and modify your details. This profile is used when you join a club, so the club
			can add you to their page seamlessly.
		</p>

		<div style="margin-top: 2rem;">
			<button class="cta-btn" onclick={() => window.open('https://clubs.iiit.ac.in', '_blank', 'noopener,noreferrer')}>
				Open Clubs Portal
				<ArrowUpRight size={16} />
			</button>
		</div>
	</div>
</div>