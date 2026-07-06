<script lang="ts">
	import { goto } from '$app/navigation';
	import { ArrowLeft } from '@lucide/svelte';
</script>

<svelte:head>
	<title>Welcome to IIIT | IIIT Hyderabad Intro to Portals Guide</title>
	<meta name="description" content="Welcome to IIIT Hyderabad — your journey begins here. A guide to all campus portals, services, and tools." />
</svelte:head>

<div class="detail-overlay" style="view-transition-name: card-welcome">
	<div class="detail-content">
		<button class="back-link" onclick={() => goto('/')} aria-label="Go back">
			<ArrowLeft size={16} /> Back
		</button>

		<h1>Welcome to IIIT</h1>
		<p class="subtitle">Your journey begins here</p>

		<div class="section-divider"></div>

		<h2>Congratulations!</h2>
		<p>
			You've made it to IIIT. As a new member of this community, you now have access to a wide
			range of digital resources and portals that will support your journey throughout your time here.
		</p>

		<h2>What is this guide?</h2>
		<p>
			This guide walks you through the essential portals and services you will use throughout your
			time at IIIT. From setting up your LDAP account to accessing the campus WiFi, submitting
			assignments on Moodle, and checking your grades on the Moodle, we've got you covered.
		</p>

		<div class="section-divider"></div>

		<div class="info-box">
            <h3>Built by Students, for Students</h3>
            <p>Most of IIIT's portals and infrastructure are open-source or built in-house by students. As you settle in, consider contributing, fix a bug, add a feature, take ownership of the tools you use every day.</p>
		</div>
	</div>
</div>